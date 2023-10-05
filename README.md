# fix-laravel-getting-env-file-value-permanently

```php

$envFilePath = base_path('.env');
        $dotenv = Dotenv\Dotenv::createImmutable(dirname($envFilePath), basename($envFilePath));
        $dotenv->load();

        return $_ENV[$key] ?? $default;

```
