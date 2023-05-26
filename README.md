# docker

```
docker-compose up -d
```

# connect to db

## psql

```
psql -hlocalhost -p54321 -Udocker -dgis
```

## with pgadmin docker

*** Since there are troubles with multiple pg-admins in each setup, I decided to remove it and just have one pgadmin on my pc (in a docker***

```
docker run -d --env PGADMIN_DEFAULT_EMAIL=docker@opengis.ch --env PGADMIN_DEFAULT_PASSWORD=docker -p 5050:80 dpage/pgadmin4:6.6
```

*** but it does not work - installed it now. fock it***

### Means:

- URL: http://localhost:5050/
- Username: docker@opengis.ch
- Password: docker

### Connect to pg
- Port: 54322 (NOT 54321!)
- Username: docker

### Connect to pg if it would be in the docker compose (workaround, but not used here)

```
dave@dave-ThinkPad-T590:~/dev/signedav/pg-docker-setup$ docker network ls
NETWORK ID     NAME                      DRIVER    SCOPE
e9dec349f9ad   bridge                    bridge    local
4cf36170d84a   host                      host      local
c2277d795bbb   none                      null      local
f7c53bee8c17   pg-docker-setup_default   bridge    local
dave@dave-ThinkPad-T590:~/dev/signedav/pg-docker-setup$ docker network inspect pg-docker-setup_default
```

Here you find an ip "IPv4Address" connect there with the normal port (like 172.18.0.2:5432)
