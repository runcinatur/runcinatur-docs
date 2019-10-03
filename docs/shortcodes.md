---
id: shortcodes
title: Shortcodes
---

## Shortcodes

To create a shortcode go to Names.php file located in Shortcodes folder.

```
  namespace App\Shortcodes;
  trait Names {
    public $names = [
        //'shortcode' => 'Controller@method',
    ];
  }
```
To register a shortcode just add your name as key in names array and a method from any controller as value. 

```
  namespace App\Shortcodes;
  trait Names {
    public $names = [
        //'shortcode' => 'Controller@method',
        'my_pretty_shortcode' => 'UserController@pretty_shortcode',
    ];
  }
```

All params will be pass to the first param of your controller method if exist.
The controller method need render a view for shortcode.