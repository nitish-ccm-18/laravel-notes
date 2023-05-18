# Laravel Notes


## Check PHP version and Larvel Project Version
```
php --version

php artisan -V
```

## How a Larvel works ? 
1. Entry point for all requests to a Laravel application is the public/index.php file.


2. Here it will check if system is down or not
it it is up then it will 
    1. loads the Composer generated autoloader definition, and then retrieves an instance of the php

    2. create an instance of laravel application from bootstrap/app.

3. Incoming request is sent to either the HTTP kernel or the console kernel
    1. HTTP kernel, located in app/Http/Kernel.php.
    <br>
    Defines an array of bootstrappers that will be run before the request is executed. These bootstrappers configure error handling, configure logging, detect the application environment, and perform other tasks that need to be done before the request is actually handled.
    <br>
    The HTTP kernel also defines a list of HTTP middleware that all requests must pass through before being handled by the application. These middleware handle reading and writing the HTTP session, determining if the application is in maintenance mode, verifying the CSRF token, and more.

## Service Provider
```
One of the most important kernel bootstrapping actions is loading the service providers for your application. All of the service providers for the application are configured in the config/app.php configuration file's providers array.

Service providers are responsible for bootstrapping all of the framework's various components, such as the database, queue, validation, and routing components. Essentially every major feature offered by Laravel is bootstrapped and configured by a service provider. Since they bootstrap and configure so many features offered by the framework, service providers are the most important aspect of the entire Laravel bootstrap process.
```

## Routing 
```
   One of the most important service providers in your application is the App\Providers\RouteServiceProvider. This service provider loads the route files contained within your application's routes directory. 

   Once the application has been bootstrapped and all service providers have been registered, the Request will be handed off to the router for dispatching. The router will dispatch the request to a route or controller, as well as run any route specific middleware. 
```

