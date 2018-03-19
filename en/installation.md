# Installation

> The page describes how to install the blog.

### Download Project

You can install PJ Blog by issuing the Composer `create-project` command in your terminal:

```shell
composer create-project jcc/blog
```

Alternatively, you may install it via `git clone`:

```shell
git clone git@github.com:jcc/blog.git
```

### Install Dependencies

#### Install PHP Dependencies

Install the PHP dependencies:

```shell
composer install
```

#### Install Front-end Dependencies

###### Install Laravel Mix, Vuejs, and other Front-end Dependencies:

```shell
npm install
```

or

```shell
yarn
```

###### Compile the assets

You can compile once:
```shell
npm run dev
// or
// yarn run dev
```

Alternatively, you can compile and run the watcher:

```shell
npm run watch
// or
// yarn run watch
```

To compile for production:

```shell
npm run production
// or
// yarn run production
```

### Modify App Configuration

Copy the `.env.example` to `.env`:

```shell
cp .env.example .env
```

Afterward, run the `blog:install` artisan command:

```shell
php artisan blog:install
```

> You must configure your web server's document/web root to be the `public` directory.
> 
> The `index.php` in this directory serves as the entry point for all HTTP page requests in your application.
> 
> Of course, you can learn more about `Laravel` in the [Laravel Docs](https://laravel.com/docs/5.5)
