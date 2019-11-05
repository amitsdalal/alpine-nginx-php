# Docker PHP-FPM 7.3 & Nginx 1.16 on Alpine Linux
Example PHP-FPM 7.3 & Nginx 1.16 setup for Docker, build on [Alpine Linux](http://www.alpinelinux.org/).
The image is only +/- 35MB large.

Repository: https://github.com/amitsdalal/alpine-nginx-php


* Built on the lightweight and secure Alpine Linux distribution
* Very small Docker image size (+/-35MB)
* Uses PHP 7.3 for better performance, lower cpu usage & memory footprint
* Optimized for 100 concurrent users
* Optimized to only use resources when there's traffic (by using PHP-FPM's ondemand PM)
* The servers Nginx, PHP-FPM and supervisord run under a non-privileged user (nobody) to make it more secure
* The logs of all the services are redirected to the output of the Docker container (visible with `docker logs -f <container name>`)
* Follows the KISS principle (Keep It Simple, Stupid) to make it easy to understand and adjust the image


[![Docker Pulls](https://img.shields.io/docker/pulls/amitdalal/alpine-nginx-php.svg)](https://hub.docker.com/r/amitdalal/alpine-nginx-php/)
[![Docker image layers](https://images.microbadger.com/badges/image/amitdalal/alpine-nginx-php.svg)](https://microbadger.com/images/amitdalal/alpine-nginx-php)
![nginx 1.16.1](https://img.shields.io/badge/nginx-1.16-brightgreen.svg)
![php 7.3](https://img.shields.io/badge/php-7.3-brightgreen.svg)
![License MIT](https://img.shields.io/badge/license-MIT-blue.svg)


## Usage

Start the Docker container:

    docker run -d -p 80:8080 amitdalal/alpine-nginx-php

See the PHP info on http://localhost, or the static html page on http://localhost/test.html

Or mount your own code to be served by PHP-FPM & Nginx

    docker run -d -p 80:8080 -v ~/my-codebase:/var/www/html amitdalal/alpine-nginx-php
