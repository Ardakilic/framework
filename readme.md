## Laravel 4.2 Framework with phpseclib's Mcrypt polyfill + PHP8 suport

*For PHP7.x, please check [4.2-no-mcrypt](https://github.com/Ardakilic/laravel-framework-4.2-no-mcrypt-extension-check/tree/4.2-no-mcrypt) branch.*

This repository holds Laravel 4.2 Framework code with softened Mcrypt extension check. Additionally, the repository holds PHP8 compatibility for routes.

If you're still using Laravel 4.2 for whatever reason, and you need to run it in newer PHP versions, and if the package manager does not have `php{version}-mcrypt` packages, you either need a polyfill for mcrypt, or install mcrypt over pecl. However, pecl is not available everywhere, and feels a bit hacky if you'd ask me.

This repository removes `extension_loaded()` check from Laravel 4.2's core, and uses [phpseclib/mcrypt_compat](https://github.com/phpseclib/mcrypt_compat) library for `mcrypt_*` functions for the cases where Mcrypt is not installed as an extension.

No other code is manipulated, you can see this repository is a fork of the main project.

To install this fork, simply add/modify these lines in your `composer.json` of your Laravel project, and install new dependencies:

```
{
    "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/Ardakilic/laravel-framework-4.2-no-mcrypt-extension-check"
        }
    ],
    "require": {
        "laravel/framework": "dev-4.2-no-mcrypt-php8"
    }
}
```

Below is the original ReadMe:

## Laravel Framework (Kernel)

[![Build Status](https://travis-ci.org/laravel/framework.svg)](https://travis-ci.org/laravel/framework)
[![Total Downloads](https://poser.pugx.org/laravel/framework/d/total.svg)](https://packagist.org/packages/laravel/framework)
[![Latest Stable Version](https://poser.pugx.org/laravel/framework/v/stable.svg)](https://packagist.org/packages/laravel/framework)
[![Latest Unstable Version](https://poser.pugx.org/laravel/framework/v/unstable.svg)](https://packagist.org/packages/laravel/framework)
[![License](https://poser.pugx.org/laravel/framework/license.svg)](https://packagist.org/packages/laravel/framework)

> **Note:** This repository contains the core code of the Laravel framework. If you want to build an application using Laravel 4, visit the main [Laravel repository](https://github.com/laravel/laravel).

## Laravel PHP Framework

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable, creative experience to be truly fulfilling. Laravel attempts to take the pain out of development by easing common tasks used in the majority of web projects, such as authentication, routing, sessions, queueing, and caching.

Laravel is accessible, yet powerful, providing powerful tools needed for large, robust applications. A superb inversion of control container, expressive migration system, and tightly integrated unit testing support give you the tools you need to build any application with which you are tasked.

## Official Documentation

Documentation for the framework can be found on the [Laravel website](http://laravel.com/docs).

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](http://laravel.com/docs/contributions).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell at taylor@laravel.com. All security vulnerabilities will be promptly addressed.

### License

The Laravel framework is open-sourced software licensed under the [MIT license](http://opensource.org/licenses/MIT)
