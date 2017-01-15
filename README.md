# toastr-laravel
toastr.js for Laravel 5.*

**Bower**

to install plugin via Bower run

***bower install toastr***

###1
Link to toastr.css  ```<link href="toastr.css" rel="stylesheet"/>```

###2 
Link to toastr.js  ```<script src="toastr.js"></script>```


###3
toastr
======

Easy [toastr.js](http://codeseven.github.io/toastr/) notifications for Laravel 5.*, a ported version of Laravel 4 Toastr by [kamaln7](https://github.com/kamaln7/toastr)

Installation
------------

1. Either run `composer require nilsenj/toastr-laravel dev-1.0-stable` 
or add `"nilsenj/toastr-laravel": "dev-1.0-stable"` to the `require` key in `composer.json` and run `composer install`

2. Add `'nilsenj\Toastr\ToastrServiceProvider',` to the `providers` key in `config/app.php`
3. Add `'Toastr'          => 'nilsenj\Toastr\Facades\Toastr',` to the `aliases` key in `config/app.php`

Usage
-----

Include jQuery and [toastr.js](http://codeseven.github.io/toastr/) and plugin styles in your master view template  

after everything is done do
``` html
{!! Toastr::render() !!}
```
in your template just bofore body closing tag or after toastr.js script instantiated in your file.


You can use these methods in your controllers to insert a toast:
  - `Toastr::warning($message, $title = null, $options = [])` - add a warning toast
  - `Toastr::error($message, $title = null, $options = [])` - add an error toast
  - `Toastr::info($message, $title = null, $options = [])` - add an info toast
  - `Toastr::success($message, $title = null, $options = [])` - add a success toast
  - `Toastr::add($type: warning|error|info|success, $message, $title = null, $options = [])` - add a toast
  - **`Toastr::clear()` - clear all current toasts** for now it's always on

### Setting custom Toastr options

You can set custom options for Toastr. Run:

``` php
php artisan vendor:publish
```

to publish the config file for Toastr. Then edit `config/toastr.php` and set the `options` array to whatever you want to pass to Toastr. These options are set as the default options and can be overridden by passing an array of options to any of the methods in the **Usage** section.

###for example###

```
<?php

return [
    'options' => 
    ["progressBar" => true,
    "positionClass" =>"toast-bottom-right",
    "preventDuplicates"=> false,
    "showDuration" => 300,
    "hideDuration" => 1000,
    "timeOut" => 5000,
    "extendedTimeOut" => 1000,
    "showEasing" => "swing",
    "hideEasing"=> "linear",
    "showMethod" => "fadeIn",
    "hideMethod" => "fadeOut"]
    ];
    
```

---
For a list of available options, see [toastr.js' documentation](http://codeseven.github.io/toastr/demo.html).
