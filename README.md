# Magento Extension Quality Program Coding Standard

### :warning: Versions 3.0.0 and above of the MEQP Coding Standard are for Magento 1.x code only.
To check Magento 2.x code use [Consolidated Magento Coding Standard](https://github.com/magento/magento-coding-standard).

[![Build Status](https://travis-ci.org/magento/marketplace-eqp.svg?branch=master)](https://travis-ci.org/magento/marketplace-eqp)

Magento EQP Coding Standard is a set of rules and sniffs for [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) tool.

It allows automatically check your code against some of the common Magento and PHP coding issues, like:
- raw SQL queries;
- SQL queries inside a loop;
- direct class instantiation;
- unnecessary collection loading;
- excessive code complexity;
- use of dangerous functions;
- use of PHP superglobals;
- code style issues and many others.

**Magento Extension Quality Program Coding Standard** consists of one ruleset - MEQP1 for Magento 1.x.

## Installation

Install all dependencies via [Composer](https://getcomposer.org):
```sh
$ composer create-project --repository=https://repo.magento.com magento/marketplace-eqp magento-coding-standard
```
You’re required to authenticate; see [Get your authentication keys](http://devdocs.magento.com/guides/v2.0/install-gde/prereq/connect-auth.html) for details.

## Usage
```sh
$ cd magento-coding-standard
```
Select the standard to run with PHP_CodeSniffer. To check Magento extension run:
```sh
$ vendor/bin/phpcs /path/to/your/extension --standard=MEQP1
```
By default, PHP_CodeSniffer will check any file it finds with a `.inc`, .`php`, `.js` or `.css` extension. To check design templates you can specify `--extensions=php,phtml` option.

To check syntax with specific PHP version set paths to php binary dir:
```sh
$ vendor/bin/phpcs --config-set php7.0_path /path/to/your/php7
$ vendor/bin/phpcs --config-set php5.4_path /path/to/your/php5.4
```
## Fixing Errors Automatically

PHP_CodeSniffer offers the PHP Code Beautifier and Fixer (`phpcbf`) tool. It can be used in place of `phpcs` to automatically generate and fix all fixable issues. We highly recommend run following command to fix as many sniff violations as possible:
```sh
$ vendor/bin/phpcbf /path/to/your/extension --standard=MEQP1
```
## Marketplace Technical Review
To make sure your extension will pass CodeSniffer checks of Magento Marketplace Technical Review, you could run `phpcs` command with `--severity=10` option.
```sh
$ vendor/bin/phpcs /path/to/your/extension --standard=MEQP1 --severity=10 --extensions=php,phtml
```
**All severity 10 errors must be fixed in order to successfully pass Level 1 CodeSniffer checks.**
 
## Requirements

* PHP >=5.5.0
* [Composer](https://getcomposer.org)
* [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) 3.*

> Notice: PHP and Composer should be accessible globally.

## Contribution

Please feel free to contribute new sniffs or any fixes or improvements for the existing ones.
