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
docker exec -it web composer install
```

You can now access [website](http://0.0.0.0:6060) and [phpMyAdmin](http://0.0.0.0:7070).

For more information see [documentation](./docs/README.md).

## Links

* [Drupal Global Training Day](https://groups.drupal.org/node/512931)
* [Drupal](https://www.drupal.org/)
