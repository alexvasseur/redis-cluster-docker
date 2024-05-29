# DRAFT / WIP


# TODO
- test 3 node stop / start
- sentinel will require external IP to be 127.0.0.1 to work thru docker networking vs internal ip address
- test with Grafana Prometheus in docker compose
- test persistence and restart scenario
- test connectiong with Redis Insight


# Parking lot notes


## Options

Configure version, username or password as you see fit in the `.env` file.

## Single node, HA or cluster


The HA and cluster mode can be started or added to an existing running single node or HA setup.

Example of running a single node
```
docker compose up
```

Example of running a three nodes cluster
```
docker compose up rec1 rec2 rec3
```
or also equivalent
```
docker compose --profile cluster up
```

Example of running one node and then later, scale with one additional node for HA
```
docker compose up
# and later...
docker compose --profile ha
# could also add the 3rd node using --profile cluster or directly
docker compose up rec3
```

## Clean up

You may restart the container and they should recover previous state.

Else just restart from scratch using
```
docker compose rm
```
or
```
docker compose --profile cluster up --force-recreate
```
