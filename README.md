# Apache Guacamole with Caddy HTTPS Reverse Proxy

## Purpose
- Automatic TLS certificate management
- Lightweight, as less setup as possible
- All containers deployed from a single docker-compose.yml

1. Create your own free domain with duckdns
2. Prepare the database container following the steps in reference #1
3. Create docker image caddy:duckdns using the Dockerfile
4. Edit Caddyfile and docker-compose.yml with your subdomain, duckdns API key, and database password (they should all be the same)
5. Deploy stack using docker-compose.yml

## Recommendations
- use a separate Portainer Docker container to manage containers
- use specific versions in the Dockerfile as recommended by Caddy dockerhub page

## Aha's
- you can't use localhost:8080 because the caddy container will look at itself instead of the guacamole container
- you can reference a container by its name from a different container (i.e. http://guacamole:8080)

## References
1. https://www.systems.dance/2021/01/apache-guacamole-and-docker-compose/
2. https://registry.hub.docker.com/_/caddy
