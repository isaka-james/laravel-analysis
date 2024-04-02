<div align="center">
  <p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>
  <h1>🚀  Web-Artisan Engineering  🤵‍♂</h1>

  
  <p>
    <img src="https://komarev.com/ghpvc/?username=isaka-laravel&label=Visitors&color=0e75b6&style=flat" alt="since 2 April,2024" />
  </p>
</div>


## What's this about? 🤔
I've crafted this for those who have a deep love for **PHP**. It's not just for the *framework users*, but also for those curious about the magic behind this popular PHP framework.

This serves as an understanding of how Laravel works, an operational tutorial, and offers unique ways to optimize along the way. You're welcome to delve deeper into Laravel and advance your skills.

So, I'm eager and grateful to share the inner workings of Laravel with you fella!

#### My Thoughts 💭:
Big thanks to [@taylorotwell](https://github.com/taylorotwell) for making *Laravel* framework accessible to all. If you're looking for someone to follow or sponsor, he's a great choice!

![image](https://github.com/isaka-james/laravel-analysis/assets/76619967/50ecc113-679f-4b1c-85d9-13a424da4e9e)

> "Make developers' lives easier, and you'll be heaven-bound for sure."
— Yours Truly


#### Contributions Welcome! 🎉
Laravel is a vast PHP framework with a plethora of features and technologies. I warmly welcome all corrections, suggestions, and new ideas to this analysis. Together, let's help fellow web-artisans better understand this framework.



<h1 align="center" style="margin-top: 40px;margin-bottom:40px;font-weight:700;"> Let's Get Set Up 🛠️</h1>

## Blueprint 🗺️

- [**Installing Laravel**](#installing-laravel)
- [**Altenative ways of installing Laravel**](#another-way)
- [**Setting up the project/Configuring**](#setting-up-the-project)
- [**Launching Laravel Project**](#testing-the-configuration)
- [**Laravel Basic Tree**](#laravels-basic-tree)
- [**Diving into Laravel Engineering**](#lets-dive-in-%EF%B8%8F)
- [**Jump into your interest Laravel part**](#-jump-to-your-interest-)
- [**LICENSE**](#-jump-to-your-interest-)

  


## Installing Laravel:
>First off, according to the official *Laravel* documentation, you'll need to have PHP and Composer installed on your system to create and use Laravel projects.

![image](https://github.com/isaka-james/laravel-analysis/assets/76619967/c18c4a6a-e9fa-46da-ad37-5e726b2ae22f)

To create a new Laravel project, use this command:
```bash
composer create-project laravel/laravel:^11.0 laravel-project
```

Alternatively, you can use the Laravel installer:
```bash
composer global require laravel/installer
laravel new laravel-project
```

If you're wondering what *Composer* is, it's an application-level dependency manager for PHP. Check out Composer's [official website](https://getcomposer.org/doc/00-intro.md) for more info.

## Another Way:
For the geeks among us, here's another method:

```bash
git clone https://github.com/laravel/laravel.git
cd laravel
composer install
```
Using this method, you'll need to change the file .env-example to .env, which contains the environment variables for your application.
>Notice that the vendor directory is not present initially. After running the composer command, the vendor directory will be created, containing the composer dependencies. We'll explore this further later on.

## Setting Up the Project:
By default, Laravel uses sqlite database. However, for this analysis, we'll use mysql:

Update the .env file as follows:

Before:

```.env
DB_CONNECTION=sqlite
# DB_HOST=127.0.0.1
# DB_PORT=3306
# DB_DATABASE=laravel
# DB_USERNAME=root
# DB_PASSWORD=
```

After:

```.env
DB_CONNECTION=sqlite
DB_HOST=localhost
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=
```

Assuming you have a database called *laravel*, customize these credentials as needed.

Ensure you've created your database using  [mariadb](https://www.vinchin.com/database-tips/install-mariadb-on-windows-linux-macos.html) or [phpmyadmin](https://docs.phpmyadmin.net/en/latest/setup.html).

Next, run this command to initialize the pre-defined tables that come with Laravel, such as session storage:

```bash
php artisan migrate
```

## Testing the Configuration:

```bash
php artisan serve
```
>By default, Laravel listens on port 8000. After running this command, open your browser and go to http:localhost:8000 to see the default page.
>![image](https://github.com/isaka-james/laravel-analysis/assets/76619967/b3fe35aa-4e09-472c-9ade-b2b229c04f8a)

## Laravel's Basic Tree:
The tree is quite large, so I've placed it in a separate file. You can view the Laravel Tree [here](/non-laravel/tree.md).

## Let's Dive In 🏊‍♂️
Now that you've seen Laravel's default page, let's delve into what's behind the scenes.

We'll start with the artisan file, [here](artisan.md).

<h1 align="center" style="margin-top: 40px;margin-bottom:40px;font-weight:700;"> Jump to Your Interest 🚀</h1>

## License
[MIT](LICENSE)
