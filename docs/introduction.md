---
id: introduction
title: Introduction
sidebar_label: Get started with Runcinatur
---


## What is Runcinatur?

Runcinatur is a framework for WordPress plugins. A way to make plugins more professional and escalable.

## Installation

Using composer 

```
composer create-project jjs4ntos/runcinatur
```

## Structure

Runcinatur is structured with MVC (Model, View and Controller) :

### Model
The models are located in folder src/Models. They can represent Entities from your database.
```
namespace App\Models;

use App\Models\Model;

class Example extends Model {

}
```

### View
The views are located in folder src/frontend. Obviusly they represent the visual of a page.
Commonly receive variables from controllers.
A view must be responsible only to show your data.
Runcinatur use [Blade](https://github.com/jenssegers/blade) to build views.

```
<div class="wrap">
    @if(true)
	    <h1>Runcinatur framework</h1>
    @endif
</div>
```

### Controller
The controllers playing in middlefield. They can manipulate models editing, adding, deleting and send 
variables to view.

```
<?php 
namespace App\Controllers;

use App\Controllers\Controller;

class ExampleController extends Controller {

}
```