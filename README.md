## Laravel library to backup the database and upload a copy to OneDrive.

[![Latest Stable Version](http://poser.pugx.org/leolopez/backup/v)](https://packagist.org/packages/leolopez/backup) 
[![Total Downloads](http://poser.pugx.org/leolopez/backup/downloads)](https://packagist.org/packages/leolopez/backup) 
[![Latest Unstable Version](http://poser.pugx.org/leolopez/backup/v/unstable)](https://packagist.org/packages/leolopez/backup) 
[![License](http://poser.pugx.org/leolopez/backup/license)](https://packagist.org/packages/leolopez/backup) 
[![PHP Version Require](http://poser.pugx.org/leolopez/backup/require/php)](https://packagist.org/packages/leolopez/backup)

## Installation

Install the package by the following command,

    composer require leolopez/backup
    
## Register the Service Provider

Add the provider in `config/app.php` int `providers` section.
    
    Leolopez\Backup\BackupServiceProvider::class
    
## Add Facade

Add the Facade to your `config/app.php` into `aliases` section,

    'Backup' => \Leolopez\Backup\Facades\Backup::class,

## Publish the Assets

Run the following command to publish config file,

    php artisan vendor:publish --provider="Leolopez\Backup\BackupServiceProvider"
    
## Register your credentials

Add the credentials of your microsoft account into `.env` file.

    TENANT_ID='-----' 
    CLIENT_ID='-----'
    CLIENT_SECRET='-----'
    USERNAME='-----'
    PASSWORD='-----'

## Register the crontab
Run the task every day at 1am.

    crontab -e

    0 1 * * * /usr/bin/php /var/www/html/project/artisan backup:create
