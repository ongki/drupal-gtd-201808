# Drupal Global Training Day setup

* [Documentation](./docs/README.md)

## Quick start

For Ubuntu run 

```
sudo apt-get update

sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

And then read https://unix.stackexchange.com/questions/363048/unable-to-locate-package-docker-ce-on-a-64bit-ubuntu

Confirm installation

```
docker --version
docker-compose --version
```

```
git clone https://gitlab.com/testudio/drupal-gtd.git app
cd app
mkdir web
docker-compose up -d --build
echo "Hello" > web/index.html
```

Check URL.

Install Drupal

```
rm -rf web
docker exec -it web composer install
docker exec -it web composer site-install-docker-ci
```

## Links

* [Drupal Global Training Day](https://groups.drupal.org/node/512931)
* [Drupal](https://www.drupal.org/)
