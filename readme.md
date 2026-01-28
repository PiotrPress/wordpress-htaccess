# WordPress `.htaccess`

This is `.htaccess` files for setup, in which WordPress is installed in a `wp-core` directory and `wp-content` directory is moved outside a core directory.

## Installation via `composer.json` file

```json
{
  "require": {
    "piotrpress/wordpress-htaccess": "^2.0"
  },
  "scripts": {
    "post-update-cmd": [
      "cp vendor/piotrpress/wordpress-htaccess/res/.htaccess .htaccess",
      "cat vendor/piotrpress/wordpress-htaccess/res/wp-core/.htaccess.cache > wp-core/.htaccess",
      "cat vendor/piotrpress/wordpress-htaccess/res/wp-core/.htaccess.security >> wp-core/.htaccess",
      "cat vendor/piotrpress/wordpress-htaccess/res/wp-core/.htaccess.default >> wp-core/.htaccess"
    ]
  }
}
```

If you have WordPress **Multisite** enabled, use one of the following commands to copy appropriate file instead of `.htaccess.default`:

Multisite **subdomain** installation:

```shell
cat vendor/piotrpress/wordpress-htaccess/res/wp-core/.htaccess.subdomain >> wp-core/.htaccess
```

Multisite **subdirectory** installation:

```shell
cat vendor/piotrpress/wordpress-htaccess/res/wp-core/.htaccess.subdirectory >> wp-core/.htaccess
```

## Resources

Check out example implementation in the [piotrpress/wordpress](https://github.com/PiotrPress/wordpress) package.

## Requirements

- `Apache` or compatible, e.g. `LiteSpeed` server
- `FollowSymLinks` directive enabled
- `AllowOverride` directive enabled
- `mod_rewrite` module enabled 
- `mod_alias` module enabled for security rules
- `mod_headers`, `mod_mime` and `mod_expires` modules enabled for cache rules

## License

[MIT](license.txt)