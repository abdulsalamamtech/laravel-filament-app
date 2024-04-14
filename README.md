<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

You may also try the [Laravel Bootcamp](https://bootcamp.laravel.com), where you will be guided through building a modern Laravel application from scratch.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains thousands of video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.


## Project
This project is a laravel filament basic application


## Developer
For more information about the developer of this project, 
please visit  [Dev. AbdulsalamAmtech](https://bit.ly/abdulsalamamtech).


## Laravel Filament Application

- **[Laravel Filament](https://filamentphp.com/)**


### Install a new laravel project
```cli
    
    laravel new filament-app

```


### Setting up the database and models
create database migration add all necessary relationships
eg [user, owner, patient, treatment]

Run migration
```cli

    php artisan migrate

```    

### Disable mass assignment
For brevity in this guide, we will disable Laravel's mass assignment protection. 
Filament only saves valid data to models so the models can be unguarded safely.
```php

    // add Model::unguard() to the boot() method of app/Providers/AppServiceProvider.php
    use Illuminate\Database\Eloquent\Model;
 
    public function boot(): void
    {
        Model::unguard();
    }

```


### Install filament package
Install filament --with-all-dependencies
```cli

    composer require filament/filament:"^3.2" -W

    // Or ignore platform requirements

    composer require filament/filament:"^3.2" -W --ignore-platform-req=ext-intl

```


### Install the filament panels
```php

    php artisan filament:install --panels

```
it will ask for the ID? [admin]
you can enter admin

Read more on [how to get started with the filament panels](https://filamentphp.com/docs/3.x/panels/getting-started)


### Create a user from the terminal
make sure you have run migration before this!
```php

    php artisan make:filament-user

```
Then you can now login to the admin dashbord 
localhost:8000/admin/login


# Introducing resources
In Filament, resources are static classes used to build CRUD interfaces for your Eloquent models. They describe how administrators can interact with data from your panel using tables and forms.
```cli

    php artisan make:filament-resource Patient

    // Or this will generate the resource base on your model
    php artisan make:filament-resource Patient --generate

    // You can also add soft delete
    php artisan make:filament-resource Patient --generate --soft-deletes

    // You can also generate the view
    php artisan make:filament-resource Patient --generate --view

```
Visit localhost:8000/admin/patients in your browser and observe 
a new link called "Patients" in the navigation


### Navigation icons
To change the navigation icons
visit [heroicons](https://heroicons.com)

```php
    protected static ?string $navigationIcon = 'heroicon-o-rectangle-stack';

    protected static ?string $navigationIcon = 'heroicon-o-flag';

    protected static ?string $navigationIcon = 'heroicon-o-rectangle-stack';

```


### Navigation
To change the navigation properties
visit [filament navigation](https://filamentphp.com/docs/3.x/panels/navigation)

The filament automatically use the table name and model attributes

```php

    // To change the label name
    protected static ?string $navigationLabel = 'New Name';

    protected static ?string $navigationLabel = 'Patients';

    // To group the list
    protected static ?string $navigationGroup = 'Services';

    // To change the route link by default it will take the models name
    protected static ?string $slug = 'patients-service';

```



## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
