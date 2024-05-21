Use `value` method on the query builder to execute a more efficient query when you only need to fetch a specific field when retrieving a single record.

```php
// Fetch the whole fields of the record, then get the `post_count` attribute.
Statistic::where('user_id', 4)->first()->post_count;

// Fetch only the `post_count` attribute's value.
Statistic::where('user_id', 4)->value('post_count');
```
