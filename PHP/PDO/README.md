# PDO

PDO (PHP Data Objects) is used for database connections. The extension is available as a PECL extension for PHP 5.0 and shipped by default with PHP 5.1.

## Set connection

It is strongly recommended to create PDO connections like this:

```php
$database = "";
$host = "";
$user = "";
$password = "";

$PDO = new \PDO("mysql:dbname=".$database.";host=".$host, $user, $password);
$PDO->setAttribute(\PDO::ATTR_ERRMODE, \PDO::ERRMODE_EXCEPTION);
$PDO->setAttribute(\PDO::ATTR_DEFAULT_FETCH_MODE, \PDO::FETCH_OBJ);
```

- `PDO::ERRMODE_EXCEPTION` must be used in order to get exceptions instead of errors
- `PDO::FETCH_OBJ` is strongly recommended in order to get objects instead of arrays when fetching data from the database

## Prepared statements

For security reasons, it is strongly recommended to use prepared statements instead of directly executing the query on the database.

Example:
```php
$sql = $PDO->prepare($query);
$sql->bindValue(":value", $value, \PDO::PARAM_STR);
$sql->execute();
```

