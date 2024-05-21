If you want to check whether a model was recently created, use `wasRecentlyCreated` model attribute.

```php
$user = User::updateOrCreate(
    ['name' => 'Oussama'],
    ['emal' => 'oussamaOtherEmail@mail.com']
);

return $user->wasRecentlyCreated;   // Return boolean.
                                    // True if the record is recently created, False otherwise.
```