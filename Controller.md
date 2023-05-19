# Controllers
It is one of the pillars of MVC architecture.Controllers contain all logic to done a task.Controllers are mainly store request handling logic

## Basic Controllers
1. Create Controller

```
php artisan make:controller TestController

```

2. Write some dummy code 
```
    // Return My Profile containing name and roll no
    public function profile () {
        return 'Name : Nitish Goswami,Gender : Male,Roll No : 7019';
    }
```

3. Create Route in routes/web.php

```
// Include TestController
use App\Http\Controllers\TestController;
Route::get('/test-point', [TestController::class,'showMyName']);
```

4. Run Project and accesss 127.0.0.1:8000/test-point
