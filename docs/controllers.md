---
id: controllers
title: Controllers
sidebar_label: Controllers
---

## The midfield player

Controllers are responsible for applying their business rule between the view and the model.
The controllers must be responsible for the decision making logic. 

To create controllers using gear just type:

`
    php gear controller User
`

This command will create a Controller like:

```
<?php 
namespace App\Controllers;

use App\Controllers\Controller;

class UserController extends Controller {

}
```

## Controllers and Views

The controller is like the best friend of the view, him send variables to views.
Supposed that we created a view named "index.blade.php" to show a Hello World:

```

<div class="wrap">

	<h1>{{ $hello }}</h1>

</div> 

```
In the controller we would do that: 

```
<?php 
namespace App\Controllers;

use App\Controllers\Controller;

class UserController extends Controller {

    public function index() {
        $hello = "Hello World!";
        echo $this->generateView("index", [ "hello" => $hello ]);
    }

}
```

The method generateView receive a view name without blade extension and a array with variables and their names.

## Controllers and Router

Controller methods must be called when a particular url is requested.
To link url to methods go to routes.php located in src/ and add a new route

```
$router->get("/hello-world", "UserController@index");
```
with a post request

```
$router->post("/hello-world", "UserController@index");
```

and continue with

```
$router->delete("/hello-world", "UserController@index");
```

```
$router->put("/hello-world", "UserController@index");
```

or if you wants to create a admin page

```
$router->register_admin_page("Title of Page", "name-of-page", "UserController@index");
```
