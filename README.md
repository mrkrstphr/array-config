# periwinkle/array-config

> Allows for using native PHP files as config files in PHP!

Using YAML and XML as configuration scripts in PHP projects has become prolific. However, this comes with the overhead of having to validate, process, and convert
those configuration files to PHP to be used.

What if you could just use native PHP arrays for configuration files?

**Now you can!**

periwinkle/array-config brings revolutionary support to PHP to use PHP in PHP.

## Installation

periwinkle/array-config can be installed via Composer:

```
composer require perwinkle/array-config
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
$config = require 'configs/database.php';
```

No need to parse Yaml! No need to parse Xml!

## Framework Support

Ping your favorite neighborhood framework developer, and tell them you want the
ability to use native PHP config files in their projects!

## Seriously

Yeah, I know you can just cache the result of the Yaml or Xml parsing so that it
doesn't have to be done over and over again, but there's no valid reason to use
it in the first place.

**Just use PHP.**
