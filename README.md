# fix-laravel-getting-env-file-value-permanently

```php
Overwrite method env in #path=vendor/laravel/framework/src/Illuminate/Support/helpers.php 
```

```php

if (!function_exists('env')) {
    /**
     * Gets the value of an environment variable.
     *
     * @param  string  $key
     * @param  mixed  $default
     * @return mixed
     */
    function env($key, $default = null)
    {
        $envFilePath = base_path('.env');
        $dotenv = Dotenv\Dotenv::createImmutable(dirname($envFilePath), basename($envFilePath));
        $dotenv->load();

        return $_ENV[$key] ?? $default;
        // return Env::get($key, $default);
    }
}

```
