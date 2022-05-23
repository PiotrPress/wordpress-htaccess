# WordPress `.htaccess`

This is a webroot directory `.htaccess` file for setup, in which WordPress is installed in a `wp-core` directory and `wp-content` directory is moved outside a core directory.

## Installation via `composer.json` file

```json
{
  "require": {
    "piotrpress/wordpress-htaccess": "^1.0"
  },
  "scripts": {
    "post-update-cmd": "cp vendor/piotrpress/wordpress-htaccess/res/.htaccess ./.htaccess"
  }
}
```

## Resources

Check out example implementation in the [piotrpress/wordpress](https://github.com/PiotrPress/wordpress) package.

## Requirements

- Apache Server with `mod_rewrite` module enabled.

## License

[MIT](license.txt)