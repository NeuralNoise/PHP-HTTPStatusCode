# PHP HTTPStatusCode library

[![Latest Stable Version](https://poser.pugx.org/josantonius/HTTPStatusCode/v/stable)](https://packagist.org/packages/josantonius/HTTPStatusCode) [![Latest Unstable Version](https://poser.pugx.org/josantonius/HTTPStatusCode/v/unstable)](https://packagist.org/packages/josantonius/HTTPStatusCode) [![License](https://poser.pugx.org/josantonius/HTTPStatusCode/license)](LICENSE) [![Codacy Badge](https://api.codacy.com/project/badge/Grade/166477cc273f4896a832580b77b2d8d7)](https://www.codacy.com/app/Josantonius/PHP-HTTPStatusCode?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=Josantonius/PHP-HTTPStatusCode&amp;utm_campaign=Badge_Grade)[![Total Downloads](https://poser.pugx.org/josantonius/HTTPStatusCode/downloads)](https://packagist.org/packages/josantonius/HTTPStatusCode) [![Travis](https://travis-ci.org/Josantonius/PHP-HTTPStatusCode.svg)](https://travis-ci.org/Josantonius/PHP-HTTPStatusCode) [![PSR2](https://img.shields.io/badge/PSR-2-1abc9c.svg)](http://www.php-fig.org/psr/psr-2/) [![PSR4](https://img.shields.io/badge/PSR-4-9b59b6.svg)](http://www.php-fig.org/psr/psr-4/) [![CodeCov](https://codecov.io/gh/Josantonius/PHP-HTTPStatusCode/branch/master/graph/badge.svg)](https://codecov.io/gh/Josantonius/PHP-HTTPStatusCode)

[Versión en español](README-ES.md)

PHP library to get the meaning from HTTP response status codes.

---

- [Requirements](#requirements)
- [Installation](#installation)
- [Available Methods](#available-methods)
- [Quick Start](#quick-start)
- [Usage](#usage)
- [List in JSON format](#list-in-json-format)
- [Tests](#tests)
- [TODO](#-todo)
- [Contribute](#contribute)
- [Repository](#repository)
- [License](#license)
- [Copyright](#copyright)

---

## Requirements

This library is supported by **PHP versions 5.6** or higher and is compatible with **HHVM versions 3.0** or higher.

## Installation

The preferred way to install this extension is through [Composer](http://getcomposer.org/download/).

To install **PHP HTTPStatusCode library**, simply:

    $ composer require Josantonius/HTTPStatusCode

The previous command will only install the necessary files, if you prefer to **download the entire source code** you can use:

    $ composer require Josantonius/HTTPStatusCode --prefer-source

You can also **clone the complete repository** with Git:

  $ git clone https://github.com/Josantonius/PHP-HTTPStatusCode.git

Or **install it manually**:

[Download HTTPStatusCode.php](https://raw.githubusercontent.com/Josantonius/PHP-HTTPStatusCode/master/src/HTTPStatusCode.php):

    $ wget https://raw.githubusercontent.com/Josantonius/PHP-HTTPStatusCode/master/src/HTTPStatusCode.php

[Download HTTPStatusCodeCollection.php](https://raw.githubusercontent.com/Josantonius/PHP-HTTPStatusCode/master/src/HTTPStatusCodeCollection.php):

    $ wget https://raw.githubusercontent.com/Josantonius/PHP-HTTPStatusCodeCollection/master/src/HTTPStatusCodeCollection.php

## Available Methods

Available methods in this library:

## - Get meaning from an HTTP response code:

```php
HTTPStatusCode::get($code, $lang, $size);
```

| Attribute | Description | Type | Required | Default
| --- | --- | --- | --- | --- |
| $code| HTTP response code. | mixed | Yes | |
| $lang| Language for definition: 'es' or 'en' | string | No | 'en' |
| $size| Definition size: 'short' or 'large' | string | No | 'short' |

**# Return** (string|false) → HTTP status code definition or false if not exists

## - Get all meanings in a array:

```php
HTTPStatusCode::getAll($lang);
```

| Attribute | Description | Type | Required | Default
| --- | --- | --- | --- | --- |
| $lang| Language for definition: 'es' or 'en' | string | No | 'en' |

**# Return** (array|false) → all definitions of HTTP response codes

## Quick Start

To use this library with **Composer**:

```php
require __DIR__ . '/vendor/autoload.php';

use Josantonius\HTTPStatusCode\HTTPStatusCode;
```

Or If you installed it **manually**, use it:

```php
require_once __DIR__ . '/HTTPStatusCode.php';

use Josantonius\HTTPStatusCode\HTTPStatusCode;
```

## Usage

Example of use for this library:

### - Get the short english meaning of an HTTP response code:

```php
HTTPStatusCode::get(200);
```

### - Get the short spanish meaning of an HTTP response code:

```php
HTTPStatusCode::get(200, 'es');
```

### - Get the detailed english meaning of an HTTP response code:

```php
HTTPStatusCode::get(200, 'en', 'large');
```

### - Get the detailed spanish meaning of an HTTP response code:

```php
HTTPStatusCode::get(200, 'es', 'large');
```

### - Get the short english meaning of an HTTP response code:

```php
HTTPStatusCode::get(200, 'en', 'short');
```

### - Get the short spanish meaning of an HTTP response code:

```php
HTTPStatusCode::get(200, 'es', 'short');
```

### - Get a english HTTP response code array:

```php
HTTPStatusCode::getAll();
```

### - Get a spanish HTTP response code array:

```php
HTTPStatusCode::getAll('es');
```

## List in JSON format

[Go to the resource](https://gist.github.com/Josantonius/0a889ab6f18db2fcefda15a039613293).

## Tests 

To run [tests](tests) you just need [composer](http://getcomposer.org/download/) and to execute the following:

    $ git clone https://github.com/Josantonius/PHP-HTTPStatusCode.git
    
    $ cd PHP-HTTPStatusCode

    $ composer install

Run unit tests with [PHPUnit](https://phpunit.de/):

    $ composer phpunit

Run [PSR2](http://www.php-fig.org/psr/psr-2/) code standard tests with [PHPCS](https://github.com/squizlabs/PHP_CodeSniffer):

    $ composer phpcs

Run [PHP Mess Detector](https://phpmd.org/) tests to detect inconsistencies in code style:

    $ composer phpmd

Run all previous tests:

    $ composer tests

## ☑ TODO

- [ ] Add new feature.
- [ ] Improve tests.
- [ ] Improve documentation.
- [ ] Refactor code for disabled code style rules. See [phpmd.xml](phpmd.xml) and [.php_cs.dist](.php_cs.dist).

## Contribute

If you would like to help, please take a look at the list of
[issues](https://github.com/Josantonius/PHP-HTTPStatusCode/issues) or the [To Do](#-todo) checklist.

**Pull requests**

* [Fork and clone](https://help.github.com/articles/fork-a-repo).
* Run the command `composer install` to install the dependencies.
  This will also install the [dev dependencies](https://getcomposer.org/doc/03-cli.md#install).
* Run the command `composer fix` to excute code standard fixers.
* Run the [tests](#tests).
* Create a **branch**, **commit**, **push** and send me a
  [pull request](https://help.github.com/articles/using-pull-requests).

## Repository

The file structure from this repository was created with [PHP-Skeleton](https://github.com/Josantonius/PHP-Skeleton).

## License

This project is licensed under **MIT license**. See the [LICENSE](LICENSE) file for more info.

## Copyright

2016 - 2018 Josantonius, [josantonius.com](https://josantonius.com/)

If you find it useful, let me know :wink:

You can contact me on [Twitter](https://twitter.com/Josantonius) or through my [email](mailto:hello@josantonius.com).