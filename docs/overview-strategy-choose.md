# Choose the right strategy

Strategies are collections of tasks that defines a certain way to deploy your application. This page gives you an overview of all available strategies after explaining how to choose a default strategy and how to give a particular host its own strategy.

## Set up a default strategy

Simply set up your `default` configuration to the strategy of your choice. See the overview below to help you choose the right strategy.

```php
// config/deploy.php

'default' => 'basic',
```

## Give a particular host its own strategy

In the example below, `dev.domain.com` and `staging.domain.com` will be using the `basic` strategy whereas the production host `domain.com` will be using the `local` strategy.

```php
// config/deploy.php

'default' => 'basic',

'hosts' => [
    'dev.domain.com' => [],
    'staging.domain.com' => [],  
    'domain.com' => [
        'strategy' => 'local',
    ],  
]
```

## Overview of available strategies

| Strategy | Description | Quick schema |
| - | - | - |
| **basic** ([doc](strategy-basic.md)) | Simple deployment process that takes place inside the host intself | ![Overview basic schema](https://user-images.githubusercontent.com/3642397/38679147-4369458c-3e63-11e8-8888-e062dcbbff09.png) |
| **local** ([doc](strategy-local.md)) | Builds your release locally and upload it to your server when it's ready. | ![Overview local schema](https://user-images.githubusercontent.com/3642397/38679148-43898e82-3e63-11e8-9810-3d5d81116a2a.png) |


Learn how to create your own strategy [here](overview-strategy-create.md).