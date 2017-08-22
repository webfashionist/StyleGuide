# Passwords

## Hashing passwords

To create a password hash, it is strongly recommended to use the PHP function `password_hash()` [PHP manual](https://secure.php.net/manual/en/function.password-hash.php).

```php
echo password_hash("your_strong_password", PASSWORD_DEFAULT);
```

Returns a hashed password with the `$2y$` identifier. Be aware, that when using `PASSWORD_DEFAULT`, the algorithm may change with newer PHP versions.

## Verifying passwords

To verify passwords, it is strongly recommended to use `password_verify()` [PHP manual](https://secure.php.net/manual/en/function.password-verify.php).

```php
var_dump(password_verify("your_strong_password", "your_hash"));
```

The function returns `true` if the hash does match, `false` if it doesn't. 

**Note**: `password_verify()` is safe against timing attacks.


## Rehashing passwords

Rehashing passwords makes sense if the options (e.g. the cost value) or the algorithm of the hash changes. See the PHP manual for further information about [password_needs_rehash()](https://secure.php.net/manual/en/function.password-needs-rehash.php).

