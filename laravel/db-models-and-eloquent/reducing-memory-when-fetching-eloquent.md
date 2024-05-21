Sometimes we need to load a huge amount of data into memory. For example:

```php
$orders = Order::all();
```

But this can be slow if we have really huge data, because Laravel prepares objects of the Model class. In such cases, Laravel has a handy function `toBase()`

```php
$orders = Order::toBase()->get();
//$orders will contain `Illuminate\Support\Collection` with objects `StdClass`.
```

By calling this method, it will fetch the data from the database, but it will not prepare the Model class. Keep in mind it is often a good idea to pass an array of fields to the `get` method to fetch only the neccessary fields.

Source: https://github.com/LaravelDaily/laravel-tips/blob/master/db-models-and-eloquent.md#reduce-memory