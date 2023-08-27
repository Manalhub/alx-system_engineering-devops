[![task-3.png](https://i.postimg.cc/nh9N283H/task-3.png)](https://postimg.cc/9DVxXk3S)


# Scaled-Up Web Infrastructure Design

## (Web Server):
- Nginx installed as the web server to serve static content.
- Handles static content and forwards dynamic requests to the application servers via the load balancer.

## (Application Server):
- Application server hosts the dynamic part of the website, processing user requests, accessing the database, and generating dynamic content.

## (Database):
- MySQL database operates as a primary-replica (master-slave) cluster for data redundancy.
- Both primary and replica nodes can accept read requests.

## Load Balancer Cluster (HAProxy):
- HAProxy configured as a cluster with two instances to distribute traffic across the application servers.
- Clustering enhances fault tolerance, improves performance, and provides high availability.

## Why Adding Separate Servers and Clustering:
- Adding the new server has allowed us to separate each component (webserver; Nginx, Application server; code base and Database; MySQL) in there own server and yet having one extra server with all the components to serve as a backup if any of the components or server fails. Each server is being monitored and has a firewall.

- **Load Balancer Cluster:** Clustering load balancer instances provides redundancy and fault tolerance. If one instance fails, the other can continue distributing traffic, ensuring high availability.

By separating components onto dedicated servers and clustering the load balancer, the infrastructure is better equipped to handle increased traffic and maintain stability and performance.
