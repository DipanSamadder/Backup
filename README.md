<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## Basic installation

### Step 1: You can install this package via composer using:

```
composer require spatie/laravel-backup
```


### Step 2: To publish the config file to config/backup.php run:
```
php artisan vendor:publish --provider="Spatie\Backup\BackupServiceProvider"
```

### Step 3: If you only need to backup the db, run:
```
php artisan backup:run --only-db
```


### Step 4: If you only need to backup the files, and want to skip dumping the databases, run:
```
php artisan backup:run --only-files

```
## Adminer installation

```
composer require onecentlin/laravel-adminer
```

### Update config/app.php
```
'providers' => [
    ...
    Onecentlin\Adminer\ServiceProvider::class,
];
```

### Publish config and theme file

```
php artisan vendor:publish --provider="Onecentlin\Adminer\ServiceProvider"
```

#### Created Files
config file: config/adminer.php
theme file: public/adminer.css


### Setup for middleware group supported

Modify config/adminer.php : 'middleware' => 'adminer',

Modify app/Http/Kernel.php file with adminer in $middlewareGroups

```
protected $middlewareGroups = [
    ...
    'adminer' => [
        \App\Http\Middleware\EncryptCookies::class,
        \Illuminate\Session\Middleware\StartSession::class,
        // TODO: you may create customized middleware to fit your needs
        // example uses Laravel default authentication (default protection)
        \Illuminate\Auth\Middleware\Authenticate::class,
    ],
];
```

## Access adminer
Open URL in web browser
```
http://[your.domain.com]/adminer
```



