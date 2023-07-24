```php
test('the codebase does not contain any debugging code')
    ->expect(['dd', 'dump', 'ray', 'var_dump', 'print_r'])
    ->not->toBeUsed();
```

```php
test('the codebase does not reference env variables outside of config files')
    ->expect('env')
    ->not->toBeUsed();
```

```php
test('Application files use strict types')
    ->expect('App')
    ->toUseStrictTypes();
```

```php
test('Mailables are extending the correct class')
    ->expect('App\Mail')
    ->toBeClasses()
    ->classes->toBeFinal() // optional
    ->classes->toExtend('Illuminate\Mail\Mailable')
    ->classes->toImplement('Illuminate\Contracts\Queue\ShouldQueue'); // optional
```

```php
test('Models are extending the correct class')
    ->expect('App\Models')
    ->toBeClasses()
    ->classes->toBeFinal() // optional
    ->classes->toExtend('Illuminate\Database\Eloquent\Model');
```

```php
test('Providers are extending the correct class')
    ->expect('App\Providers')
    ->toBeClasses()
    ->classes->toBeFinal() // optional
    ->classes->toExtend('Illuminate\Support\ServiceProvider')
    ->classes->toImplementNothing();
```

```php
test('Requests are extending the correct class')
    ->expect('App\Http\Requests')
    ->toBeClasses()
    ->classes->toBeFinal() // optional
    ->classes->toExtend('Illuminate\Foundation\Http\FormRequest');
```

```php
test('API Controllers are not extending anything')
    ->expect('App\Http\Controllers\Api')
    ->toBeClasses()
    ->classes->toBeFinal() // optional
    ->classes->toExtendNothing();
```

```php
test('Commands are extending the correct class')
    ->expect('App\Console\Commands')
    ->toBeClasses()
    ->classes->toBeFinal() // optional
    ->classes->toExtend('Illuminate\Console\Command');
```

```php
test('Tests are using strict types and have the correct suffix')
    ->expect('Tests')
    ->toUseStrictTypes()
    ->and('Tests\Feature')->toHaveSuffix('Test')
    ->and('Tests\Unit')->toHaveSuffix('Test');
```
