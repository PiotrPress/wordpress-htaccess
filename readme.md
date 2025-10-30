# WordPress `.htaccess`

This is a webroot directory `.htaccess` file for setup, in which WordPress is installed in a `wp-core` directory and `wp-content` directory is moved outside a core directory.

## Installation via `composer.json` file

```json
{
  "require": {
    "piotrpress/wordpress-htaccess": "^1.0"
  },
  "scripts": {
    "post-update-cmd": [
      "cp vendor/piotrpress/wordpress-htaccess/res/.htaccess .htaccess",
      "cp vendor/piotrpress/wordpress-htaccess/res/wp-core/.htaccess wp-core/.htaccess"
    ]
  }
}
```

If you have WordPress **Multisite** enabled, use one of the following commands to copy appropriate `.htaccess` file instead.

Multisite **subdomain** installation:

```shell
cp vendor/piotrpress/wordpress-htaccess/res/wp-core/.htaccess.subdomain wp-core/.htaccess
```

Multisite **subdirectory** installation:

```shell
cp vendor/piotrpress/wordpress-htaccess/res/wp-core/.htaccess.subdirectory wp-core/.htaccess
```

## Resources

Check out example implementation in the [piotrpress/wordpress](https://github.com/PiotrPress/wordpress) package.

## Requirements

Apache server with `mod_rewrite` module enabled or compatible e.g. LiteSpeed server.

## License

[MIT](license.txt)