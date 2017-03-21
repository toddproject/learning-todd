
# Start all components
By default it will start: The todd server, Rabbitmq, etcd and 2 todd agents
```
make start
```

Both agents should register automatically, you can check using:
```
✗ make agents
docker exec -it dockercompose_toddserver_1 todd agents
UUID		EXPIRES	ADDR		FACT SUMMARY		COLLECTOR SUMMARY
9c5992d8622e	23s	172.25.2.3	Addresses, Hostname	get_addresses, get_hostname
7d9d0f0ec4b7	23s	172.25.1.3	Hostname, Addresses	get_addresses, get_hostname
```

You can increase the number of agents with docker-compose using `docker-compose scale`
```
docker-compose scale agent-hq=2 agent-dc=3
```
> New agents will register automatically, you can check using `make show-agents`

# Create groups and tests in todd
Once all components are up, you need to create some `groups` and `tests`.
you can create the predefined groups and tests with:
```
make init
```
it will create 2 groups `agent-hq` and `agent-dc` and create 3 tests.

# access the Todd Cli

```
make cli
```
