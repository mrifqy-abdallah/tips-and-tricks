If you create a Laravel boilerplate as a "starter" for other devs, and you're not in control of what THEY would later fill in Model's `$fillable` or `$guarded`, you may use `forceFill` method.

```php
$team->update(['name' => $request->name])
```

What if "name" is not in Team model's `$fillable`? Or what if there's no `$fillable`/`$guarded` at all?

```php
$team->forceFill(['name' => $request->name])
```
This will "ignore" the `$fillable` for that one query and will execute no matter what.

Source: https://github.com/LaravelDaily/laravel-tips/blob/master/db-models-and-eloquent.md#force-query-without-fillableguarded