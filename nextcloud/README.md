ABOUT
=====

This repository contains the configuration Files to run a Nextcloud instance via docker-compose.

The setup is:
1. Nextcloud Container run with Apache Webserver
2. Nextcloud cron companion Container, for running cron Tasks
3. Redis 
4. MariaDb as Database
5. Nginx Reverse Proxy
6. LetsEncrypt comanion Container for Nginx

Only The Nginx Reverse Proxy is accessable via Internet.
This Setup has 2 seperate docker networks, the default nework and proxy_tier.
Default is Nextcloud App, Redis and the Maria DB container.
proxy_tier is Nexctloud App, Nginx Reverse Proxy and LetsEncrypt companion.

This allows seperation, so the Database and Redis are not accessable from Nginx to add additional security.

The LetsEncrypt Companion creates and renews the ssl certificate for the specified Domain automatically.


Steps to run
------------

1. Clone this repository and enter nextcloud folder
2. Edit docker-compose.yml  and db.env and enter your configuration with db passwords, redis password, domain name etc...
3. Run with docker compose up -d 
