# PoC Saltstack

Docker Compose file which creates a Salt master and minion(s). The Salt master auto accepts all minions. Used for testing the salt master with > 1000 minions. 

## Start the stack

Start the salt master and 1 minion.

```shell
docker-compose up -d
```

## Registering minions

When using `auto_accept: False` (default setting) every minion needs to be accepted. List minions waiting for keys to be accepted. This part can be skipped when using this repo as is.

```shell
docker-compose exec master salt-key -L
```

Accept all pending keys for all minions

```shell
docker-compose exec master salt-key -A
```

## Using salt

Scale some extra minions

```shell
docker-compose up --scale minion=5
```

Run some commands on the minions

```shell
```
