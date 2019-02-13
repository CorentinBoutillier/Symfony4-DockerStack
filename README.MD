# Stack Docker Symfony 3 

## PHP / NGINX / MySql / Phpmyadmin

symfony/docker-compose.yml : 

```
remplacer : "localhost" dans 
- "traefik.frontend.rule=Host:localhost"
par votre nom de domaine "vpsXXXXX.ovh.net"

Personalisez vos identifiant MySql : 

    MYSQL_ROOT_PASSWORD: rootpassword
    MYSQL_DATABASE: mydb
    MYSQL_USER: mydbuser
    MYSQL_PASSWORD: mydbpassword
```

traefik-proxy/traefik.toml :

```
remplacer "votre@email.fr" dans
email = "votre@email.fr"
par votre email
```
Puis exécuter les commandes suivantes :

```
cd traefik-proxy
docker network create traefik-proxy
docker-compose up -d
cd ../symfony
docker network create cb-symfony
docker-compose build
docker-compose up -d
```

Ensuite, déposer le code dans le dossier html

Aller sur votre nom de domaine vpsXXXXX.ovh.net

Phpmyadmin : vpsXXXXX.ovh.net:8080