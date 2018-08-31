# Drupal Global Training Day setup

## Quick start

1. You need to install [docker](https://docs.docker.com/install/) and [docker compose](https://docs.docker.com/compose/install/).
  
  Once installed, you should be able to very by opening terminal (CLI) 
  on your machine and running
  
  ```
  $ docker -v
  Docker version 18.06.0-ce, build 0ffa825
  $ docker-compose -v
  docker-compose version 1.22.0, build f46880f
  ```
  
  If you can't see the versions, try to reinstall prerequisites.
  
2. Clone [current repository](https://gitlab.com/testudio/drupal-gtd-dev/)
  
  ```
  git clone git@gitlab.com:testudio/drupal-gtd-dev.git
  ```
  
3. Initialise containers

  ```
  cd drupal-gtd-dev
  docker-compose up -d --build
  docker exec -it webgtd composer install
  ```
 
  
  You can now access [website](http://0.0.0.0:6060) and [phpMyAdmin](http://0.0.0.0:7070).
  
  Database credentials can be found in `docker-compose.yml` file.
  
  For more information see [documentation](./docs/README.md).
  
## Debugging
  
Verify that all containers are running. Command ``

```
docker-compose ps
```

should return

```
   Name                 Command               State               Ports             
------------------------------------------------------------------------------------
mysql        docker-entrypoint.sh mysqld      Up      3306/tcp, 33060/tcp           
phpmyadmin   /run.sh supervisord -n           Up      0.0.0.0:7070->80/tcp, 9000/tcp
webgtd       docker-php-entrypoint apac ...   Up      0.0.0.0:6060->80/tcp   
```

`docker-compose logs` should give you more insight if you have any issues.
  
## Links

* [Drupal Global Training Day](https://groups.drupal.org/node/512931)
* [Drupal](https://www.drupal.org/)
