PhpBuiltinServer
================

Codeception extension to start and stop PHP built-in web server for your tests.

| Codeception Branch       | PhpBuiltinServer Branch |
|--------------------------|-------------------------|
| **Codeception 1.x**      | **1.1.x**               |
| **Codeception 2.0**      | **1.2.x**               |
| **Codeception 2.1, 2.2** | **1.3.x**               |
| **Codeception 2.3**      | **1.4.x**               |
| **Codeception 3.0, 4.0** | **1.5.x**               |
| **Codeception 5.0**      | **master**              |

## Minimum requirements

* Codeception 5.0
* PHP 8.1

## Installation

1. Install [Codeception](http://codeception.com) via Composer
2. Add `atg-ltd/codeception-phpbuiltinserver: "*"` to your `composer.json`
3. Run `composer install`
4. Include extensions into `codeception.yml` configuration:

## Configuration

### general example

``` yaml
paths:
    output: _output
    tests: .
    data: _data
    helpers: _helpers
extensions:
    enabled:
        - Codeception\Extension\PhpBuiltinServer
    config:
        Codeception\Extension\PhpBuiltinServer:
            hostname: localhost
            port: 8000
            autostart: true
            documentRoot: tests/_data
            startDelay: 1
            phpIni: /etc/php8/apache2/php.ini
```

### example for projects based on Symfony
``` yaml
paths:
    output: _output
    tests: .
    data: _data
    helpers: _helpers
extensions:
    enabled:
        - Codeception\Extension\PhpBuiltinServer
    config:
        Codeception\Extension\PhpBuiltinServer:
            hostname: localhost
            port: 8000
            autostart: true
            documentRoot: ../web
            router: ../web/app.php
            directoryIndex: app.php
            startDelay: 1
            phpIni: /etc/php8/apache2/php.ini
            logDir: _log
```
