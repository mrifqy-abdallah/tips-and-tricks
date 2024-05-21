If you need to execute a simple SQL query, without getting any results - like changing something in DB schema, you can just do `DB::statement()`.

```php
DB::statement('DROP TABLE users');
DB::statement('ALTER TABLE projects AUTO_INCREMENT=123');
```

Source: https://github.com/LaravelDaily/laravel-tips/blob/master/db-models-and-eloquent.md#good-old-sql-query