## Controllers

To create a controller use the xerophy console command

```javascript
php xerophy.php make:controller {ControllerName}
```

You will get something like this

```javascript
<?php

namespace App\Controllers;

class HomeController extends Controller
{
    public function index()
    {
         //Write code here
    }
}

```


### Render method
This method is responsible to render a view
```javascript
<?php

namespace App\Controllers;

class HomeController extends Controller
{
    public function index()
    {
        $this->render('index.html.twig');
    }
}
```



### Accepting the coming arguments

```javascript
<?php

namespace App\Controllers;

class HomeController extends Controller
{
    public function show($id)
    {
        
    }
}
```


### Dependency injection in a method

```javascript
<?php

namespace App\Controllers;

class HomeController extends Controller
{
    public function index(Request $request)
    {
        
    }
}
```


### Accepting the coming arguments and Dependency injection

```javascript
<?php

namespace App\Controllers;

class HomeController extends Controller
{
    public function index(Request $request, $id)
    {
        
    }
}
```