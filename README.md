<div align="center">
  <p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>
  <h1>Advanced Web-Artisans - Laravel Understanding🤵‍♂</h1>

  
  <p>
    <img src="https://komarev.com/ghpvc/?username=isaka-laravel&label=Visitors&color=0e75b6&style=flat" alt="since 2 April,2024" />
  </p>
</div>


## What is this?
I designed this, for the people who have the love for **PHP**, not just the *framework users* but for people who want to know what is happening behind the scene in this popular PHP framework.

Hence, Then I'm very pleased to share the idea behind/inner-works of this popular PHP framework with you!

#### My Comment:
I am very grateful to this guy [@taylorotwell](https://github.com/taylorotwell) for putting *Laravel* framework public accessible, And if you're looking for someone to follow or sponsoring then considering  him will be a great choice!

![image](https://github.com/isaka-james/laravel-analysis/assets/76619967/50ecc113-679f-4b1c-85d9-13a424da4e9e)

> "Always try to make developers life easy, You'll go heaven for that"
— Me


#### Contributions:
As you know Laravel is a very large robust PHP framework with alot of features, and technologies. I am sincerely welcome all the corrections,suggestions, new ideas to this analysis, so we can help fellow web-artisans to understand better this framework.





<h1 align="center" style="margin-top: 40px;margin-bottom:40px;font-weight:700;"> Let's configure </h1>

## Setting up the Laravel Framework:
>First of all from the official documentation of *Laravel*, They recommend that we need to have PHP and Composer installed on our system inorder to create and  use the Laravel framework in our machine.
![image](https://github.com/isaka-james/laravel-analysis/assets/76619967/c18c4a6a-e9fa-46da-ad37-5e726b2ae22f)

We can  create our laravel project by this command:
```bash
composer create-project laravel/laravel:^11.0 laravel-project
```

Altenative also we can create our Laravel application by installing the *Laravel installer* globally in our machine:
```bash
composer global require laravel/installer
laravel new laravel-project
```
If you are wondering what is *composer*?, according to wikipedia:
>Composer is an application-level dependency manager for the PHP programming language that provides a standard format for managing dependencies of PHP software and required libraries. It was developed by Nils Adermann and Jordi Boggiano, who continue to manage the project.

>Also you can go to [composer official website](https://getcomposer.org/doc/00-intro.md) to know more about *composer*.

Both those are the commands that create the project called *laravel-project*.

### Altenative way of creating project
Also as a geek, you should know other ways of creating the laravel project:
```bash
git clone https://github.com/laravel/laravel.git
cd laravel
composer install
```
From the above commands, we are downloading the laravel source code directly from github using git(Also you can download manually and extract the zip), and then we are moving to the project and installing the composer dependencies.
>You can notice upon using this method, *vendor* directory is not present. But after running the *composer* command the vendor directory will be created containing the composer dependencies. We'll look further on this later.

>Also when using method you'll need to chang the file *.env-example* to *.env*, this is the  file that contains the enviroment variables for our application.

##  SetUp the Project:
By default, the *Laravel* framework uses *sqlite* database, but in this analysis we'll use *mysql* since it is easy to use and almost everybody know it:

So by saying so we'll need to change these lines from the *.env* file.

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
We've assumed that you've a database called *laravel*, as you have seen these are your database credidentials, customize them as you desire.

Make sure you've already created your database, you can use [mariadb](https://www.vinchin.com/database-tips/install-mariadb-on-windows-linux-macos.html) or [phpmyadmin](https://docs.phpmyadmin.net/en/latest/setup.html) to create your database, incase our database name is *laravel*.

After that we can run this command which like initialize the pre-tables that comes with *laravel*, i.e *session storage* and more, we'll look after them later:
```bash
php artisan migrate
```

### Finaly we can test our configurations:
```bash
php artisan serve
```
>By default *Laravel* listens on the port **8000** , so after running that command we can type on the browser *http:localhost:8000*, to see our favourite default page.
![image](https://github.com/isaka-james/laravel-analysis/assets/76619967/b3fe35aa-4e09-472c-9ade-b2b229c04f8a)

## The Basic Tree of Laravel:
The tree is somewhat large so I've put in a separate file you can see here the [Laravel Tree](/non-laravel/tree.md).

## Let's start
So now you've successfully seen the default page from *laravel*, so now we're going to know what was behind the scene.

We'll start with the artisan file, [here](artisan.md)


<h1 align="center" style="margin-top: 40px;margin-bottom:40px;font-weight:700;"> Jump to your interest analysis: </h1>



## License
[MIT License](LICENSE)
