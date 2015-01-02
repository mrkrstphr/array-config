# periwinkle/array-config

![](http://forthebadge.com/badges/built-with-love.svg)
![](http://forthebadge.com/badges/ages-12.svg)

> Allows for using native PHP files as config files in PHP!

Using YAML and XML as configuration scripts in PHP projects has become prolific. However, this comes with the overhead of having to validate, process, and convert
those configuration files to PHP to be used.

What if you could just use native PHP arrays for configuration files?

**Now you can!**

periwinkle/array-config brings revolutionary support to PHP to use PHP in PHP.

## Installation

periwinkle/array-config can be installed via Composer:

```
composer require periwinkle/array-config
```

## Usage

Let's say you had a configuration file written in Yaml:

```yaml
database:
	driver: pgsql
	host: localhost
	name: awesomedb
	user: awesomesauce
	password: mustangSally
```

With periwinkle/array-config, you can now write this configuration file as pure PHP!

```php
return [
    'database' => [
        'driver' => 'pgsql',
        'host' => 'localhost',
        'name' => 'awesomedb',
        'user' => 'awesomesauce',
        'password' => 'mustangSally'
    ]
];
```

To use this config file, simply:

```php
$config = include 'configs/database.php';
```

No need to parse Yaml! No need to parse Xml!

### Older Versions of PHP

array-config is so revolutionary, we've added support going all the way back to PHP 3!
The examples above use the short array syntax introduced in PHP 5.4. If you're living in
the past, you can still use array-config*:

```php
return array(
    'database' => array(
        'driver' => 'pgsql',
        'host' => 'localhost',
        'name' => 'awesomedb',
        'user' => 'awesomesauce',
        'password' => 'mustangSally'
    )
);
```
Usage:

```php
$config = include 'configs/database.php';
```

\* Note: Composer will not work with some older versions. For those versions, feel free
to copy the array-config source code to a directory within your project. Any directory
will do; we suggest a `functions/` or `includes/` directory if you have one.

## Framework Support

Ping your favorite neighborhood framework developer, and tell them you want the
ability to use native PHP config files in their projects!

## Seriously

Yeah, I know you can just cache the result of the Yaml or Xml parsing so that it
doesn't have to be done over and over again, but there's no valid reason to use
it in the first place.

**Just use PHP.**
