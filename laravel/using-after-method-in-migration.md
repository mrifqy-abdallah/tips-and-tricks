# Eloquent migration after
This is a simple little trick for adding columns to an existing table. For obvious reasons, you cannot use after() to a column created for your migration.

However, the `after()` method takes a closure where you can wrap your columns.

```php
$table->after('username', function ($table) {
    $table->string('address_line1');
    $table->string('address_line2');
    $table->string('city');
});
```

Source: https://janostlund.com/2022-01-01/eloquent-migration-after
