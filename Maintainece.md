# Down the server
1. Sometimes you may need to update some configuration values or perform maintenance on your website. In such cases, keeping it in maintenance mode, makes it easier for you. Such web applications which are kept in maintenance mode, throw an exception namely MaintenanceModeException with a status code of 503.
```
php artisan down
```

2. Once you finish working on updates and other maintenance, you can disable the maintenance mode on your web application using following command −
```
php artisan up
```