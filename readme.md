# API RESTful With Laravel & Heroku

**this is a little tutorial about how upate and deploy free  API**

**FIRST STEP: Creating project**

1.- Install Git Cli -> https://git-scm.com/

2.- You need create a heroku account -> https://www.heroku.com/ 

3.- Install Heroku Cli -> https://devcenter.heroku.com/articles/heroku-cli

4.- Install Composer -> https://getcomposer.org/download/ 

5.- Open your terminal and Run 'composer' command, and check if you can access to composer commands.

6.- Install Xampp -> https://www.apachefriends.org/es/index.html

7.- Run Apache and MySQL with Xampp.

8.- Go to folder /htdocs in your terminal with 'cd' command.

9.- once you are in /htdocs folder in your terminal run the next command: 

    command: composer create-project laravel/laravel AppName

10.- go to http://localhost and open AppName folder and need be into http://localhost/AppName/public

11.- ¡Congratulations! you have a new project running in your localhost

**SECOND STEP: Up to Heroku**

1.- Open your AppName project into code editor.

3.- Delete .env.example

4.- Open .gitignore file and only add this lines: 

    /vendor
    
    /node_modules
    
    /Homestead.yaml
    
    /Homestead.json
    
    .env
    
 5.- Open your teminal and go to Application in localhost and run the next commands: 
 
   git init
   
   git add .
   
   git commit -am "first commit"
   
   git status
   
   echo web: vendor/bin/heroku-php-apache2 public/> Procfile
   
   git status
   
   git add . 
   
   git commit -am "adding Procfile"
   
   heroku create NameApp -> wait to finish
   
   heroku buildpacks:set heroku/php
   
   git push heroku master -> wait to finish
   
   heroku open
   
 ¡Congratulation your laravel project is up to heroku!
 
 if you have dudes you can check this video -> https://www.youtube.com/watch?v=47B5tq9ZdW8&t=4s
  
  **THIRD STEP: Creating APIRestful**
  
  1.- create a database with https://www.freemysqlhosting.net/ and you need copy host access and got to .ENV file project add next lines: 
  
    DB_CONNECTION=mysql
    
    DB_HOST=sql3.freemysqlhosting.net
    
    DB_PORT=3306
    
    DB_DATABASE=sql3249989
    
    DB_USERNAME=sql3249989
    
    DB_PASSWORD=nDQkGrnvFj
Note: **Obviusly with your information created in freemysqlhosting** 

2.- Follow the next tutorial to describe how do an api, to fast way, **IMPORTANT: follow the tutorial since STEP 2**
https://itsolutionstuff.com/post/how-to-create-rest-api-in-laravel-5-example.html
   
when your finish you need run: 
    git add . 
    
    git commit -m "adding routes API"
    
    git status
    
    git push heroku master
    
 3.- Adding CORS: 
 
 You can install the package via Composer:

composer require spatie/laravel-cors

The package will automatically register its service provider.

The provided Spatie\Cors\Cors middleware must be registered in the global middleware group.

// app/Http/Kernel.php

protected $middleware = [
    ...
    \Spatie\Cors\Cors::class
];

php artisan vendor:publish --provider="Spatie\Cors\CorsServiceProvider" --tag="config"

if you have dudes you can watch: https://github.com/spatie/laravel-cors#laravel
