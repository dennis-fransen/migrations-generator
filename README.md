# Laravel Migrations Generator Laravel 6


[![Latest Stable Version](https://poser.pugx.org/oscarafdev/migrations-generator/v/stable)](https://packagist.org/packages/oscarafdev/migrations-generator)
[![Total Downloads](https://poser.pugx.org/oscarafdev/migrations-generator/downloads)](https://packagist.org/packages/oscarafdev/migrations-generator)
[![License](https://poser.pugx.org/oscarafdev/migrations-generator/license)](https://packagist.org/packages/oscarafdev/migrations-generator)

Generate Laravel Migrations from an existing database, including indexes and foreign keys!


## Laravel 6 installation

The recommended way to install this is through composer:

```bash
composer require oscarafdev/migrations-generator 2.0.13
```

In Laravel 5.5+ the service providers will automatically get registered. 

## Usage

To generate migrations from a database, you need to have your database setup in Laravel's Config.

Run `php artisan migrate:generate` to create migrations for all the tables, or you can specify the tables you wish to generate using `php artisan migrate:generate table1,table2,table3,table4,table5`. You can also ignore tables with `--ignore="table3,table4,table5"`

Laravel Migrations Generator will first generate all the tables, columns and indexes, and afterwards setup all the foreign key constraints. So make sure you include all the tables listed in the foreign keys so that they are present when the foreign keys are created.

You can also specify the connection name if you are not using your default connection with `--connection="connection_name"`

Run `php artisan help migrate:generate` for a list of options.

Check out Chung Tran's blog post for a quick step by step introduction: [Generate Migrations from an existing database in Laravel 4](http://codingtip.blogspot.com/2014/04/laravel-4-generate-migration-existed-dabase-laravel-4.html)

## Changelog

Changelog for Laravel Migrations Generator

### 10 December 2019: v2.0.12
* Support for Laravel 6

### 20 November 2016: v2.0.0
* Support for Laravel 5

### 20 November 2016: v1.3.0
* Add options --defaultIndexNames and --defaultFKNames to use Laravel's default generated names
* --no-interaction support
* Migrate table field comments
* Add connection to migrations if its not the default
* Bugfix:
  * --ignore doesn't ignoring the first table in the list
  * Remove backticks from index names #17
  * Drop foreign keys used incorrect key name #34
  * Remove table prefix from migrations
  * Escape table names and args
  * Map JSON columns as text
  * Boolean default results in empty string

### 25 July: v1.2.2
* Support for Laravel 4.2
* Support for named foreign keys
* Fix error with --ignore option

### 29 May: v1.2.1
* Fixed problem with char fields showing up as varchar
* Allow decimal, float, and double to be unsigned
* Allow cascading on foreign key update/delete

### 16 May: v1.2.0
* Now fully supports for enum fields
* Add support for bit fields as Boolean (Laravel Migration Limitation)

### 10 May: v1.1.1
* Fix crash when migrating tables that use enum
* Added Tests
* Major refactoring of the code

### 24 March: v1.1.0
* Ability to add entries into the Migrations Table, so that they won't be run as they already exist.
* Convert Blobs to Binary fields
* Minor Code Changes

## Thank You

Thanks to Jeffrey Way for his amazing Laravel-4-Generators package. This package depends greatly on his work.

## Contributors

Bernhard Breytenbach ([@BBreyten](https://twitter.com/BBreyten))
Oscar Fernandez ([@oscarafdev](https://www.linkedin.com/in/oscarafdev/))

## License

The Laravel Migrations Generator is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)
