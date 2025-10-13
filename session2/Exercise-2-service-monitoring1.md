[Main Menu](../README.md) | [Session 2](../session2/README.md) | [Exercise-2-service-monitoring](../session1/Exercise2-service-monitoring1.md)

# Exercise Service Monitoring

## service 3 tier network

Often sites are made scalable through load-balancing a number of servers. 
In this example we have installed three wordpress servers behind an NGINX load balancer.

All there server share the same MariaDB database which also maintains the session data across the servers.

![alt text](../session2/images/examplenetwork-loadbalance.drawio.png "Figure examplenetwork-loadbalance.drawio.png")

## running the example

```
cd minimal-minion-activemq
docker compose up -d
```

![alt text](../session2/images/wordpress1.png "Figure wordpress1.png")



![alt text](../session2/images/wordpress2.png "Figure wordpress2.png")


![alt text](../session2/images/wordpress3.png "Figure wordpress3.png")



![alt text](../session2/images/loadbalance-example1.png "Figure loadbalance-example1.png")
