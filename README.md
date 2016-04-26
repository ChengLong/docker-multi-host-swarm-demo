Orchestrating Docker with Swarm, Machine, Compose and Consul
===

This app demos how to orchestrate Docker with Swarm, Machine, Compose and Consul. Find out more at [my post](https://chengl.com/orchestrating-docker-using-swarm/).

To try the demo, follow these steps

#### 1. Create and Run Consul

```
./create_run_consul
```

#### 2. Create The Swarm

```
./create_swarm
```
#### 3. Run registrator in each host

```
./run_registrator_in_all_hosts
```

#### 4. Run the app with docker-compose

```
export CONSUL_URL=$(docker-machine ip consul):8500
docker-compose up -d
```

#### Scaling

```
docker-compose scale app=4
docker-compose scale app=2
```

#### Check Nginx conf
```
docker exec -t <load-balancer container> cat /etc/nginx/conf.d/service.conf
```

#### Check Consul UI
```
https://<Consul IP>:8500/ui
```
