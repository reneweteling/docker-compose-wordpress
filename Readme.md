# Docker compose wordpress development kit

## Booting local development

```sh
docker compose up
docker compose down
```

#### wp-config.php

```php
if($_ENV["LOCAL"] == "true"){

  // Report all PHP errors (see changelog)
  error_reporting(E_ALL);

  define( 'WP_DEBUG', true );
  define( 'WP_DEBUG_LOG', true );
  define( 'WP_DEBUG_DISPLAY', true );

  // Local docker development
  define('WP_HOME','http://localhost');
  define('WP_SITEURL','http://localhost');

  /** The name of the database for WordPress */
  define( 'DB_NAME', $_ENV["DB_NAME"]);

  /** MySQL database username */
  define( 'DB_USER', $_ENV["DB_USER"]);

  /** MySQL database password */
  define( 'DB_PASSWORD', $_ENV["DB_PASSWORD"]);

  /** MySQL hostname */
  define( 'DB_HOST', $_ENV["DB_HOST"]);
}
```

## MySql

```bash
host: localhost
port: 3310
username: wordpress
password: wordpress
```
