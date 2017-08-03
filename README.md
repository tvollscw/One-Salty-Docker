# PoC Saltstack

Docker Compose file which creates a Salt master and minion(s). The Salt master auto accepts all minions. Used for testing the salt master with > 1000 minions. 

## Start the stack

```shell
docker-compose up -d
```

## Using salt

List minions waiting for keys to be accepted

```shell
docker-compose exec master salt-key -L
```

Scale some extra minions

```shell
docker-compose up --scale minion=5
```

Accept all pending keys for all minions

```shell
docker-compose exec master salt-key -A
```

Run some commands on the minions

```shell
docker-compose exec master salt '*' test.ping
```
