The `sole` method will return exactly one record that matches the criteria. Plus:
- If no such entry is found, `NoRecordsFoundException` will be thrown
- If multiple records are found, then `MultipleRecordsFoundException` will be thrown

```php
DB::table('products')->where('ref', '#123')->sole();
```

Source: https://github.com/LaravelDaily/laravel-tips/blob/master/db-models-and-eloquent.md#find-a-single-record-from-a-database