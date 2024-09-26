# nakama oss

## setup

https://heroiclabs.com/docs/nakama/getting-started/configuration/

```
7349 GRPC
7350 HTTP
7351 HTTP for console (configurable)
9100 prometheus (optional)
```

for cluster it needs the gossip layer which seems absent from nakama OSS  
OOS load balancing works only for sticky nginx strategies such as ip_hash  
(resulting in players routed to an instance being able to play between themselves)


## what's they themselves use

- registry.heroiclabs.com/heroiclabs/nakama:3.22.0
- https://github.com/heroiclabs/nakama/tags
- https://github.com/heroiclabs/nakama/blob/v3.22.0/build/pluginbuilder/Dockerfile
- https://github.com/heroiclabs/nakama/blob/v3.22.0/go.mod


## docker composes

### local

```
docker compose -f docker-compose-local.yml up (-d)
docker compose -f docker-compose-local.yml down
```

### playrealm.net

```
docker compose up --scale gamesvc=1 (-d)
docker compose down
```

## games using this approach

- tictactoe
    - [server code](https://github.com/JosePedroDias/nakama-tictactoe)
    - [client code](https://github.com/JosePedroDias/nakama-tictactoe-client)
    - [client site](https://josepedrodias.github.io/nakama-tictactoe-client)
