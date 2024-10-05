# Cloud Migration Lab4 V1

## Target architecture solution diagram

![lab4v1](./lab4v1.png)

## Target Architecture Description

The architecture is designed to ensure high availability, redundancy, and fault recovery of the application in the cloud. The following is a detailed description of the target architecture:

- **Redundancy**
  - Multi-region deployment: The key components of the application (WebServerVM and SQLVM) will be deployed in two different geographical regions. This multi-region deployment ensures that even if one region fails, the other region can continue to provide services.
  - Multiple instances: There are independent web server and SQL database instances in each region. These instances synchronize data during normal operation to ensure data consistency and availability.
- **Failover mechanism**
  - Load balancer: Regional load balancers are deployed in each region, and global load balancers are deployed globally. Regional load balancers are responsible for distributing traffic within regions, while global load balancers are responsible for distributing traffic between regions.
  - Health check: The load balancer periodically checks the health status of WebServerVM and SQLVM. If an instance is detected to be unavailable, the load balancer automatically redirects traffic to a healthy instance.
  - Automatic failover: When a service in one region is unavailable, the global load balancer automatically redirects traffic to a service instance in another region to ensure application continuity.
- **Data synchronization and consistency**
  - Cross-region data replication: The static content of the web server and the data of the SQL database are synchronized in real time between the two regions. For WebServerVM, you can use file synchronization tools (such as rsync) to synchronize static content. For SQLVM, you can use database replication technology (such as master-slave replication of Postgresql) to synchronize data.
  - Data consistency: Ensuring data consistency between the two regions is key. By configuring appropriate synchronization and replication mechanisms, you can ensure the consistency and availability of data between the two regions.
- **High availability**
  - Minimize downtime: Through multi-region deployment and automatic failover mechanism, the downtime of the application can be controlled within 6 hours. Even if one region fails, another region can take over immediately to ensure the high availability of the application.

## Migration steps

1. **Copy virtual machines across regions**
  1. Preparation:
     - Confirm the configuration of the existing WebServerVM and SQLVM, including operating system, CPU, memory, storage, etc.
     - Select the target region and ensure that the resource and network configuration of the target region are compatible with the source region.
  2. Create virtual machines in the target region:
     - Create virtual machines with the same configuration as the existing WebServerVM and SQLVM in the target region.
     - Install and configure the necessary software and services to ensure that the environment of the new virtual machine is consistent with the source virtual machine.
  3. Data synchronization:
     - For WebServerVM, use file synchronization tools to copy static content from the source region to the target region.
     - For SQLVM, configure database replication to ensure that the database is synchronized in real time between the two regions.
2. **Load balancer configuration**
  1. Intra-region load balancer:
    - Deploy a local load balancer (such as Azure Load Balancer) in each region.
    - Configure a health check mechanism to regularly check the health status of WebServerVM and SQLVM to ensure that only healthy instances receive traffic.
  2. Global load balancer:
    - Deploy a global load balancer (such as Azure Traffic Manager) to distribute traffic to load balancers in different regions.
    - Configure traffic routing policies (such as priority routing, geographic routing, etc.) to distribute traffic based on user location and regional health status.
3. **Implement database replication and failover**
  1. Database replication:
    - Configure cross-region replication of SQL databases and select appropriate replication technologies (such as master-slave replication for Postgresql).
    - Ensure the stability and security of replication links, configure network security groups and firewall rules, and allow cross-region database replication traffic.
  2. Failover mechanism:
    - Configure an automatic failover mechanism to automatically switch to a database instance in another region when a SQL database in one region is unavailable.
    - Test the failover mechanism regularly to ensure quick response and recovery when an actual failure occurs.