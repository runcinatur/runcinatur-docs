---
id: setup
title: Setup
sidebar_label: Configuring plugin
---

## The start of plugin

All plugins made with Runcinatur started from Setup.php located in Config folder.
Setup.php file is perfect if you need create a download link or validate user licences.

## Plugin title and configuration

To set plugin informations go to index.php file located at root folder of your plugins and edit like:

```
<?php
/*
  Plugin Name: My Plugin Name
  Plugin URI: My Plugin URI
  Description: My Plugin Description
  Version: 1.0.0
  Author: Your Name
  Author URI: Your URI
*/
  // If this file is accessed directory, then abort.
  if ( ! defined( 'WPINC' ) ) {
      die;
  }
  define('PLUGIN_NAME', 'My Plugin Name');
  define('SD_PATH', plugin_dir_url( __FILE__ ));
  define('SD_PLUGIN_PATH', plugin_dir_path( __FILE__ ));
  define('URL_SCOPE', 'my-plugin-api');
  require_once 'vendor/autoload.php';
  require_once 'src/Config/Setup.php';
  require_once 'src/database/install.php';
  require_once 'src/routes.php';
```