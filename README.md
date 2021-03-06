# WP Glide

Simple integration of [Glide](http://glide.thephpleague.com/) with WordPress.

## Installation

```
composer require frozzare/wp-glide
```

## Documentation

Default url path is `/img/`. So just change `/wp-content/uploads/` to `/img/` to use Glide.

For example:

```
Before: http://local.wordpress.dev/wp-content/uploads/2015/11/stf01381_1600x800.jpg
After:  http://local.wordpress.dev/img/2015/11/stf01381_1600x800.jpg
```

You can change the upload url path with `pre_option_upload_url_path` filter.

```php
add_filter( 'pre_option_upload_url_path', function () {
  return site_url( '/img' );
} );
```

The base path can be changed with `glide/base_url` filter. To change any options for Glide you can do it with `glide/options` filter. The default options in WP Glide is:

```php
'source'   => WP_CONTENT_DIR . '/uploads',
'cache'    => WP_CONTENT_DIR . '/cache/glide',
'base_url' => '/img/'
```

For more options see [Glide setup](http://glide.thephpleague.com/1.0/config/setup/).

## Coding style

You can check if your contribution passes the styleguide by installing [PHP CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) and running the following in your WP Glide directory:

```
vendor/bin/phpcs -s --extensions=php --standard=phpcs.xml src/
```

## License

MIT © [Fredrik Forsmo](https://github.com/frozzare)
