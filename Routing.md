## Basic Routing
Write in web.php
Route::get('/endpoint',Controller::class,'function');

## Route parameters
Route::get('/endpoint/{data}',function($data){
    $msg = 'Hi your data is : '.$data;
    return $msg;
})