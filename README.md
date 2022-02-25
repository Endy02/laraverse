# Laraverse

![GitHub top language](https://img.shields.io/github/languages/top/endy02/laraverse?style=plastic) ![GitHub code size in bytes](https://img.shields.io/github/languages/code-size/endy02/laraverse?color=%23f16d18&style=plastic)

> Docker template for laravel


---

## Features

- Docker v20.10.12
- Laravel v9.2.0 
- PHP v8.0.12
- Composer v2.1.11

---

## Installation

> First you'll need to clone this repository

<br>

#### 1. Clone laraverse

```
    git clone https://github.com/Endy02/laraverse.git
```
When git ended his cloning process just go in the Laraverse directory :
```
    cd laraverse
```

<br>

#### 2. Start docker containers


```
    docker-compose up
```
> if you just want to run the contaiers as background tasks just do this :
> ```
>   docker-compose up -d
> ```

<br>

#### 3. Install laravel dependencies
> In this step you'll execute a composer command into a docker container

<br>

##### 3.1 Find the web container
> We're searching about the container id to open a bash in it.
```
    docker ps
```
> this command will help you find all the running containers, if you want to see all the container stopped :
> ```
>   docker ps -a
> ```

<br>

##### 3.2 Open a bash in the container

With a docker command you will open a bash command line in the running container.

This will be needed to execute a php artisan command for laravel.

<b>

```
    docker exec -it <container id> bash
```

</b>

> You will need to execute this command and enter in the container to execute all your php artisan instructions and manage your laravel project by the way of the command line

<br>

##### 3.3 Install all packages needed with composer


```
    composer install
```
> composer package manager will install all the package that laravel need to build up his process

---

## List of basic php command

PHP artisan have a lot of command and tool you can use be here is a basic list of command that can be usefull :
|Command|Description|
| --- | --- |
|```php artisan make:migration nameOfMigration``` | Create a specific migration|
|```php artisan migrate```|Run all the migrations created|
|```php artisan make:controller nameOfController```|Create a new controller|
|```php artisan make:model```|Create controller|

---

### License

Copyright (c) 2022 Fujyn <br>
Licensed under the <a href="https://github.com/Endy02/laraverse/blob/master/README.md">MIT license</a>.

---

### Contributing

<b>Bugs & New Features</b>

Please use the <a href="https://github.com/Endy02/laraverse/issues">issue tracker</a> to report any bugs or feature requests.