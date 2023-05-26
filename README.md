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

- URL: http://localhost:5052/
- Username: docker@opengis.ch
- Password: docker

- Port: 54322 (NOT 54321!)
- Username: docker

### Connect to pg

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
