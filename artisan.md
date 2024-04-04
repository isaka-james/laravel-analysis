<div align="center">
  <p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>
  <h1>🚀  Web-Artisan Engineering  🤵‍♂   </h1>
  <h1>artisan 📁</h1>
  
  <p>
    <img src="https://komarev.com/ghpvc/?username=isaka-laravel&label=Visitors&color=0e75b6&style=flat" alt="since 2 April,2024" />
  </p>
</div>

## Blueprint 🗺️

- [**Author**](#author-comment)
- [**Pre-Knowledge about artisan**](#pre-knowledge-about-artisan)
- [**artisan all lines of code explained**](#lets-go)
- [**What I discovered on artisan analysis**](#what-i-learnt-on-artisan-analysis)
- [**Most artisan used commands**](#some-most-used-commands)
- [**Make your own artisan commands**](#you-can-customize-your-commands)

  
## Author comment:
*Navigating the Laravel ecosystem has been challenging due to the scarcity of up-to-date resources. Despite some efforts to find current information, I've encountered deficiency of resources that accurately reflect the latest changes in Laravel. This discrepancy has made it particularly challenging to understand the many advancements and updates introduced in versions beyond Laravel 11. Consequently, I've found myself grappling with outdated materials, hindering my ability to grasp the wonders of the latest Laravel iterations.*

## Pre-knowledge about Artisan:
As per the Laravel documentation, the artisan file serves as the entry point for Laravel's Command Line Interface (CLI), enabling direct execution of Laravel commands from the CLI of your operating system.
>![image](https://github.com/isaka-james/laravel-analysis/assets/76619967/65af8aa1-4f6a-4ec2-b7d8-7e9c1465a0a1)


## Let's GO
Let's examine the artisan file line by line:


### artisan: line 1
```php
#!/usr/bin/env php
```
This is the shebang or hashbang line. If you're familiar with bash scripting, you'll recognize its purpose. It specifies the interpreter that should be used to execute the following script, in this case, **PHP**.
>While this line isn't mandatory, including it ensures compatibility across different environments. Additionally, if **PHP** is installed in a non-standard location, adjusting the shebang line accordingly is essential.

### artisan: line 2-5
```php
<?php
 
use Symfony\Component\Console\Input\ArgvInput;
   
```
The `<?php` tag starts the **PHP** script. The `use` statement brings in the `ArgvInput` class from the `Symfony\Component\Console\Input` group. This class, which is part of the `Symfony` Console part, is used by Laravel for commands on the command line. At first, I was confused because I didn't see the `Symfony` folder at the main level. But I looked closer and realized that these parts are managed by the *symfony* library inside the vendor folder. Also, I noticed something interesting: the `use` was used before any include or require lines. Later, I found out that this line could be moved after the require statement (after line 9) and it would still work fine.

### artisan: line 6-7
```php
define('LARAVEL_START', microtime(true));
   
```
This line defines the constant `LARAVEL_START`, which stores the value returned by the microtime function with the parameter true. This function returns the current `Unix timestamp` with microseconds. Although its primary purpose is to initialize a timer to measure the framework's boot-up time, I haven't encountered instances of its usage within the framework itself. Perhaps its utilization could be explored independently.

### artisan: line  8-11
```php
// Register the Composer autoloader...
require __DIR__.'/vendor/autoload.php';
    
   
```

The line before this one tells us that it's adding the Composer autoloader. Even though the libraries here are from Composer and not specifically for Laravel, let me explain a bit. This line brings in the Composer autoloader file to our script. Composer creates this file, and it's in charge of finding and loading classes and files from all the libraries we installed with Composer. When we include this file, Laravel can automatically find and use all the classes from the libraries we added with Composer. This helps keep our code organized and makes managing dependencies easier. So, once we include this file, we can use all the classes without any extra effort.

#### What is autoload.php?
The `vendor/autoload.php` file, accessible [here](vendor/autoload.php), handles autoload functionality. I won't delve further into its details as it falls outside the scope of Laravel-specific discussion.

### artisan: line 12-15
```php
// Bootstrap Laravel and handle the command...
$status = (require_once __DIR__.'/bootstrap/app.php')
    ->handleCommand(new ArgvInput);
  
exit($status);
  
```
After including app.php(using require), it obtains an instance of our Laravel application.

Then, it uses this application instance to run a command through Artisan, Laravel's command-line tool.
The command execution result, such as success or failure, is stored in the $status variable.

Then you can know what is going on `bootstrap/app.php`, [here](bootstrap/app.md)


## What I learnt on artisan analysis:
If you want to see where are the commands stored and logic implemented on their actions, go [here](/)
#### some most used commands:
```bash
php artisan list     # This command will list available Artisan commands

php artisan help migrate     # Replace 'migrate' with any command you want to see its documentation

php artisan      # Same as 'php artisan list'

php artisan make:controller Admin/HomeController    # This create a controller inside a Admin folder, like this app/Http/Controller/Admin/HomeController

php artisan make:model Logs    # This creates a Logs model like this app/Models/Logs

php artisan make:middleware FilterAllowedUsers   # This filter the http request coming to the application using custom filtering/logic, Remember to register them

php artisan migrate    # Do the migration to your laravel application

php artisan migrate:fresh    # Deleting the all the tables and do the migration again

php artisan db:seed     # Populate your database with seeders

# Have your favourite command? then pull request :)
```
#### You can customize your commands!
Also you can customize your own commands using this command:
```bash
php artisan make:command MyCustomCommand
```
Look at `app/console/Commands` to edit your custom command, for more details go [here](https://laravel.com/docs/11.x/artisan#generating-commands)

