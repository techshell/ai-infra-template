# What?

This is a collection of docker compose files to setup a flowise, n8n and traefik environment.

# How?

1. To properly allow external access to flowise or n8n you will need to setup Traefik with a specific domain name e.g. flowise.example.com and n8n.example.com
2. That will require pointing a DNS record to the hosting environment. Traefik will automatically generate a letsencrypt ssl certificate.
3. For local development this is not required, you can just use the docker host and the port associated with the service e.g. http://localhost:3000 for flowise
4. Each folder will require a .env file - copy the example and modify
5. Use docker compose commands to start, stop manage each service.

# Important Consideration

Before you start make sure you create docker network in advance to allow traefik proxy to handle routing and ssl

```
docker network create traefik
docker network create n8n
docker network create flowise
```
