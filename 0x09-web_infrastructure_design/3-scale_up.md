[![task-3.png](https://i.postimg.cc/nh9N283H/task-3.png)](https://postimg.cc/9DVxXk3S)


# Scaled-Up Web Infrastructure Design

## Server 1 (Web Server):
- Nginx installed as the web server to serve static content.
- Handles static content and forwards dynamic requests to the application servers via the load balancer.

## Server 2 (Application Server 1):
- Application server hosts the dynamic part of the website, processing user requests, accessing the database, and generating dynamic content.

## Server 3 (Application Server 2):
- Additional application server added to distribute the load and improve performance. Mirrors the functionality of Application Server 1.

## Server 4 (Database):
- MySQL database operates as a primary-replica (master-slave) cluster for data redundancy.
- Both primary and replica nodes can accept read requests.

## Load Balancer Cluster (HAProxy):
- HAProxy configured as a cluster with two instances to distribute traffic across the application servers.
- Clustering enhances fault tolerance, improves performance, and provides high availability.

## Why Adding Separate Servers and Clustering:
- **Web Server:** Separate web server offloads application servers from serving static content, improving performance and focusing application servers on dynamic requests.

- **Additional Application Server:** Another server improves scalability, preventing overloading a single server during high traffic periods.

- **Load Balancer Cluster:** Clustering load balancer instances provides redundancy and fault tolerance. If one instance fails, the other can continue distributing traffic, ensuring high availability.

By separating components onto dedicated servers and clustering the load balancer, the infrastructure is better equipped to handle increased traffic and maintain stability and performance.
