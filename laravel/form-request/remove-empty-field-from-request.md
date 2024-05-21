Imagine a profile page where user can update their info. Name and email fields are required for the update, while the password is not. For such case, you can define the Form Request as follows:

```php
class ProfileUpdateRequest extends FormRequest
{
    public function rules()
    {
        return [
            'name' => ['required', 'string', 'max:255'],
            'email' => ['required', 'email', 'string', 'max:255', Rule::unique('users')->ignore(Auth::user())],
            'password' => ['sometimes', 'required_with:old_password', 'string', 'confirmed', 'min:8'],
        ];
    }

    protected function prepareForValidation()
    {
        if ($this->password == null) {
            $this->request->remove('password');
        }
    }
}
```

The `prepareForValidation` method will remove the password field from the request if it empty. And then the password field also has the `sometimes` validation attribute, which makes the validation on password only runs if it exists in the request data. 

That way, if a user only updates their name and email, the request data will only consist of `name`+`email`; while updating the password as well will make it consist of `name`+`email`+`password`.

Defining the Form Request as such will enable you to execute the update with clearer code without any need of if-else statement or any additional code:

```php
public function update(ProfileUpdateRequest $request)
{
    auth()->user()->update($request->validated());

    return redirect()->route('profile.show')->with('success', 'Profile updated.');
}
```

Note: In case of user's password, you might want to store it as hashed. This can be easily done using eloquent's mutator.