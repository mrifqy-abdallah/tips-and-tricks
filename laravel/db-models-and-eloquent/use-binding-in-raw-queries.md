Pass an array of bindings to most raw query methods to avoid SQL injection.

```php
// This is vulnerable to SQL injection.
$fullname = request('full_name');
User::whereRaw("CONCAT(first_name, last_name) = $fullName")->get();

// Use binding instead.
User::whereRaw("CONCAT(first_name, last_name) = ?", [$fullname])->get();
```

Source: https://github.com/LaravelDaily/laravel-tips/blob/master/db-models-and-eloquent.md#remember-to-use-bindings-in-your-raw-queries