```php
test('the codebase does not contain any debugging code')
    ->expect(['dd', 'dump', 'ray', 'var_dump'])
    ->not->toBeUsed();
```

```php
test('the codebase does not reference env variables outside of config files')
    ->expect('env')
    ->not->toBeUsed();
```
