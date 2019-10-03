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