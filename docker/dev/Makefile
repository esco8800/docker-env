SHELL = /bin/sh
IMAGES_PREFIX := $(shell basename $(shell dirname $(realpath $(lastword $(MAKEFILE_LIST)))))

COMPOSER_CONTAINER_NAME := composer

docker_compose_bin := $(shell command -v docker-compose 2> /dev/null)

.PHONY : help up down  init composer-install

cli-composer:
	$(docker_compose_bin) -f ./docker-compose-build.yml run --rm "$(COMPOSER_CONTAINER_NAME)" /bin/sh

up:
	$(docker_compose_bin) up --no-recreate -d

down:
	$(docker_compose_bin) down

composer-install:
	$(docker_compose_bin) -f ./docker-compose-build.yml run --rm "$(COMPOSER_CONTAINER_NAME)" composer install --no-interaction --ansi --no-suggest
