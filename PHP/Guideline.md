# PHP Guideline

## Autoloading

* PHP classes must automatically be included with an autoloader (`spl_autoload_register()`).
* The classes must be included with `require_once`.

See [PSR-0](https://www.php-fig.org/psr/psr-0/) for more details.


## Files

* PHP code must use the long `<?php ?>` tags or the short-echo `<?= ?>` tags; it must not use the other tag variations.
* PHP files must be saved as `UTF-8` files.
* Files should either declare symbols (classes, functions, constants, etc.) or cause side-effects (e.g. generate output, change .ini settings, etc.) but should not do both.
* The closing `?>` PHP tag must be omitted from files containing only PHP.
* The last closing `?>` PHP tag may be omitted from files ending with PHP.
* PHP files including a class must have a name ending with `.class.php`
* PHP files which are always included must have a name ending with `.inc.php`



## Variables, constants, function names and class names

* Variable and function names must always be written in `camelCase`.
* All variable and constant names must start with a letter.
* Underscores in variable and constant names may be used when necessary.
* Hyphens must not be used.
* Global variables and constants must be written in `UPPERCASE`.
* Class names must be defined in `StudlyCaps`.
* Classes for PHP 5.3 and later require a defined namespace.


```php
$firstName = 'John';
$lastName = 'Doe';
```

```php
namespace Vendor\Model;

class SomeClass 
{
    const VERSION = '1.0';
}
```

## Keywords and `true`, `false`, `null`

* PHP [keywords](http://php.net/manual/en/reserved.keywords.php) must be in lower case.
* The PHP constants `true`, `false`, and `null` must be in lower case.



## Operators

* Always put spaces around operators ( `=` `+` `-` `*` `/` ), and after commas.
* Calculations should be used in brackets.

```php
$x = ($y + $z);
$values = ["Volvo", "Saab", "Fiat"];
```


## Statements

* The `=` symbol must be surrounded with one space when used for variable assignments:

```javascript
$name = "John Doe";
```


## Complex statements

* Complex statements must always use brackets.
* The opening bracket must be set in the next line after the function or class declaration.
* Before the opening bracket one space must be set.
* The closing bracket must be set on a new line, without leading spaces.
* Do not end a complex statement with a semicolon.
* Functions (and functions inside classes) must end with at least one `return` value and must not end with `exit` or `die`.

*Functions:*
```php
function toCelsius($fahrenheit) 
{
    return (5 / 9) * ($fahrenheit - 32);
}
```

*Loops:*
```php
for ($i = 0; $i < 5; $i++) {
    $x += i;
}
```


*Conditionals:*
```php
if($time < 12) {
    $greeting = "Good morning";
} elseif($time < 16) {
    $greeting = "Good day";
} else {
    $greeting = "Good evening";
}
```

* The short `if`-`else` statements must not be used for long statements.
* Very short `if`-`else` statements can be used in `return` statements of a function.

```php
function functionName($variable) 
{
    return ($variable ? "Output: ".$variable : false);
}
```


## Declarations

* Declarations must be placed on top

```php
class SomeClass 
{
    // declare variables
    private $firstName, $lastName, $price, $discount, $fullPrice;

    public function someMethod() 
    {
        // function body
    }

}
```


## Comparison

* Comparison with value and type `===` is recommended.

```php
"1" === 1 // false
1 === 1   // true
```


## SQL vs. PHP

* SQL must be used instead of complex PHP statements whenever possible. This allows better performance and less calculations on the PHP side.
* While `mysqli` and `PDO` are two possible ways to connect to a database, the recommended method is using `PDO` with prepared statements.


## Security

* `eval()`, `exec()`, `shell_exec()` must be avoided, if possible.


## Sources

* [PSR-1](https://www.php-fig.org/psr/psr-1/)
* [PSR-2](http://www.php-fig.org/psr/psr-2/)


