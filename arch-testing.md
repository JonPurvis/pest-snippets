Check for `dd`, `dump` and `ray` usage across your application

```php
test('the codebase does not have stray dd or dump usage')
    ->expect(['dd', 'dump', 'ray'])
    ->not->toBeUsed();
```
