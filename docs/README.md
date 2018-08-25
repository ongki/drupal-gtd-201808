# Drupal 8 for PHP installation instructions

## Mandatory

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

4. Install Drupal website

```
docker exec -it web composer install
docker exec -it web composer site-install-docker-ci
```

## Optional. Continuous integration.

This step is not required for training but there would be tutorial 
so if you would like to do hands on session, follow the instructions below.

1. Create Gitlab account
2. [Generate SSH key](https://docs.gitlab.com/ee/ssh/README.html#generating-a-new-ssh-key-pair) if you haven't done that before and add public key to Gitlab account.
3. Create GitHub account
4. [Generate SSH key](https://docs.gitlab.com/ee/ssh/README.html#generating-a-new-ssh-key-pair) if you haven't done that before and add public key to Gitlab account.

## Optional. Continuous delivery.

1. Create Platfrom.sh account
  * Click `Start free trial` on [Platfrom.sh home pgae](https://platform.sh/)
2. [Generate SSH key](https://docs.gitlab.com/ee/ssh/README.html#generating-a-new-ssh-key-pair) if you haven't done that before and add public key to Platform account.
