# Traefik

Use these labels on your containers:
```
- "traefik.enable=true"
- "traefik.http.routers.front_proxy.entrypoints=http"
- "traefik.http.routers.front_proxy.rule=Host(`${DOMAIN_NAME}`) || Host(`www.${DOMAIN_NAME}`)"
- "traefik.http.routers.front_proxy.middlewares=redirect-to-https@file"
- "traefik.http.routers.front_proxy-secure.entrypoints=https"
- "traefik.http.routers.front_proxy-secure.rule=Host(`${DOMAIN_NAME}`) || Host(`www.${DOMAIN_NAME}`)"
- "traefik.http.routers.front_proxy-secure.middlewares=redirect-to-non-www@file"
- "traefik.http.routers.front_proxy-secure.tls=true"
- "traefik.http.routers.front_proxy-secure.tls.certresolver=myresolver"
```
