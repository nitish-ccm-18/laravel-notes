# Views
In MVC framework, the letter “V” stands for Views. It separates the application logic and the presentation logic.
Views are stored in resources/views directory. Generally, the view contains the HTML which will be served by the
application.


### Basic view rendering
```
Route::get('/test', function() {
   return view('test');
});
```
So we can access test.php on link 127.0.0.1:/8000/test

### Passing Data to Views
```
Route::get('/test', function() {
   return view('test',[‘name’=>’Virat Gandhi’]);
});
```
Access it in our views using php syntax
```
<html>
   <body>
      <h1><?php echo $name; ?></h1>
   </body>
</html>
```
### Sharing Data with all Views
We have seen how we can pass data to views but at times, there is a need to pass data to all the views. Laravel 
makes this simpler. There is a method called share() which can be used for this purpose. The share() method will 
take two arguments, key and value. Typically share() method can be called from boot method of service provider.
We can use any service provider, AppServiceProvider or our own service provider.
Update boot method of AppServiceProvider.php
```
 public function boot()
    {
        // share data with all views
        view()->share('projectName','Example app');
    }
```
Include Routes
```
Route::get('/page1',function() {
    return View('page1');
});

Route::get('/page2',function() {
    return View('page2');
});
```
Access data in all views as per need



