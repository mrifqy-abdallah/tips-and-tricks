A simple way to seed a database in Laravel with a .sql dump file

```php
DB::unprepared(
    file_get_contents(__DIR__ . './dump.sql')
);
```

Source: https://github.com/LaravelDaily/laravel-tips/blob/master/db-models-and-eloquent.md#a-simple-way-to-seed-a-database