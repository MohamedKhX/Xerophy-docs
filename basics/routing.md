## Basic Routing

To define routes go to routes folder in web.php and register your routes there.

The most basic Xerophy routes accept a URI and a Closure,
providing a very simple and expressive method of defining routes:

```php
$router->get('/uri', function() {
    echo 'hello world';
});
```

**And you can use a controller instead of a callback function**

```php
$router->get('/uri', [HomeController::class, 'methodName']);
```

#### You can also name your routes using name method    

```php
$router->get('/uri', [HomeController::class, 'methodName'])->name('RouteName');
```


#### Available Router Methods


```php
$router->get('/uri',    [HomeController::class, 'methodName']);
$router->post('/uri',   [HomeController::class, 'methodName']);
$router->put('/uri',    [HomeController::class, 'methodName']);
$router->delete('/uri', [HomeController::class, 'methodName']);
```


#### View routes
```php
$router->view('/uri', 'viewName');
```


### Route parameters

```php
$router->get('/uri/:id', [HomeController::class, 'show']);
```

You may define as many route parameters as required by your route:

```php
$router->get('/post/:id/comment/:comment', [PostsController::class, 'show']);
```


### After and Before Events
you can run a callback function before or after the main function 

```php
$router->get('/post/:id', [PostsController::class, 'show'])
->after(function() {
    echo 'After';
})->before(function () {
    echo 'Before';
});
```


### Dependency injection in the callback function

```php
$router->get('/post/:id', function(Request $request) {
    
});
```