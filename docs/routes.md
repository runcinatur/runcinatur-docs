---
id: routes
title: Routes
---

## Router

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

