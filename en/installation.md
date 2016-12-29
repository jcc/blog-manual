# Installation

> The page is introduced how to install the blog.

### Download Project

You can install Blog by issuing the Composer `creare-project` command in your terminal:

```shell
composer create-project jcc/blog
```

Alternatively, you may also install by `git clone`  command in your terminal:

```shell
git clone git@github.com:jcc/blog.git
```

### Install Repositories

#### Install Laravel Repositories

You need to install the Laravel repositories:

```shell
composer install --no-dev
```

#### Install Front-end Repositories

###### Install the `Gulp`

```shell
npm install --global gulp
```

Alternatively, you can use `yarn` instead of `npm`:

```shell
yarn add global gulp
```

###### Install Laravel Elixir and Vuejs repositories:

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
gulp
```

Alternatively, you can also compile with watcher:

```shell
gulp watch
```

Of course, you also compile for your production:

```shell
gulp --production
```

### Modify Configuration

Copy the `.env.example` to `.env`:

```shell
cp .env.example .env
```

You can run the `blog:install` command when you set up:

```shell
php artisan blog:install
```

> You must configurate your web server's document / web root to be the `public` directory. 
> 
> The `index.php` in this directory serves as the front controller for all HTTP requests entering your application.
> 
> Of course, you can learn more about `Laravel` in the [Laravel Document](https://laravel.com/docs/5.3)
