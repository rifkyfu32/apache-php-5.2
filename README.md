This docker image is intended to work as a replacement for old legacy projects, running on old server.

Features:
* Features included from the [original repository](https://github.com/kuborgh/docker-php-5.2):
    * Based on Ubuntu 12.04
    * Apache MPM Prefork
    * PHP 5.2.17 as apache mod
    * Zend Optimizer
* Features added by [Demin](https://github.com/deminy/docker-php-5.2):
    * Enable PHP on the default site.
    * Allow [short open tag](http://php.net/manual/en/ini.core.php#ini.short-open-tag).
* Features added by Rifky:
    * Enable SSL
    * Various updates and fixes.

# Sample Docker compose file

```yaml
version: '3.6'
services:

  applegacy:
    container_name: applegacy
    image: rifkyfuady/apache-php-5.2
    ports:
      - "9080:80"
      - "9443:443"
    volumes:
      - "~/projects/example.com:/project"
      - "~/projects/example.com/000-project.conf:/etc/apache2/sites-enabled/000-project.conf"
      - "~/projects/example.com/ssl:/var/imported/ssl"
```