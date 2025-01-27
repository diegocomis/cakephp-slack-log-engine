[![Build Status](https://img.shields.io/travis/hiromi2424/cakephp-slack-log-engine/master.svg?style=flat-square)](https://travis-ci.org/hiromi2424/cakephp-slack-log-engine)
[![Coverage Status](https://img.shields.io/codecov/c/github/hiromi2424/cakephp-slack-log-engine.svg?style=flat-square)](https://codecov.io/github/hiromi2424/cakephp-slack-log-engine)
[![Total Downloads](https://img.shields.io/packagist/dt/hiromi2424/cakephp-slack-log-engine.svg?style=flat-square)](https://packagist.org/packages/hiromi2424/cakephp-slack-log-engine)
[![Latest Stable Version](https://img.shields.io/packagist/v/hiromi2424/cakephp-slack-log-engine.svg?style=flat-square)](https://packagist.org/packages/hiromi2424/cakephp-slack-log-engine)
[![Scrutinizer](https://img.shields.io/scrutinizer/g/hiromi2424/cakephp-slack-log-engine.svg)](https://scrutinizer-ci.com/g/hiromi2424/cakephp-slack-log-engine/)

## What is this?

This is CakePHP plugin to provide a log engine that post to slack using incoming webhooks.

Please see detail [how to configure webhooks on slack](https://api.slack.com/incoming-webhooks).

The engine uses [Slack for PHP](https://github.com/maknz/slack) and is just thin wrapper for the library.

## Installation

```
composer require diegocomis/cakephp-slack-log-engine
```

## Requirementscurl -sS https://getcomposer.org/installer | php

* CakePHP 4.1.7
* PHP 7.2

## Usage

### Configure log

In your app.php, you can configure like:

    'Log' => [
        'error' => [
            'className' => 'SlackLogEngine\Log\Engine\SlackLogEngine',
            // Your slack hook URL here
            'hookUrl' => 'https://hooks.slack.com/services/xxxxx/xxxxx/xxxxxxxxxx',
            // Send logs of following levels to slack
            'levels' => ['error', 'critical', 'alert', 'emergency'],
        ],
    ],

### Log options

Either `client` or `hookUrl` is required.

- `hookUrl` [string] Slack hook url.
- `client` [\Maknz\Slack\Client] Slack client instance for custom.
- `clientClass` [string(optional)] slack client class. This option is used only with `hookUrl` option.

Other available settings can be seen at [Slack for PHP Official Docs](https://github.com/maknz/slack#settings)
