# Cloud Cost Estimation for Enterprise Application Migration

## Cost Estimation Report

### Migration Costs

| **Service type**                           | Region  | **Description**                                              | Estimated monthly cost |
| ------------------------------------------ | ------- | ------------------------------------------------------------ | ---------------------- |
| Azure Migrate                              |         | There is no charge to use Azure Migrate.                     | $0.00                  |
| Bandwidth                                  |         | Internet egress, 30720 GB outbound data transfer from West US routed via Microsoft Global Network | $2,582.40              |
| Azure Database Migration Service (classic) | East US | Premium pricing tier, 4 vCore, 2 Instances X 730 Hours       | $449.68                |
| Storage Accounts                           | East US | Block Blob Storage, General Purpose V2, Flat Namespace, LRS Redundancy, Hot Access Tier, 15 TB Capacity - Pay as you go, 10 x 10,000 Write operations, 10 x 10,000 List and Create Container Operations, 10 x 10,000 Read operations, 1 x 10,000 Other operations. 1,000 GB Data Retrieval, 1,000 GB Data Write, SFTP disabled | $320.53                |
| Virtual Machines                           | East US | 21个D2 v3 (2 vCPUs, 8 GB RAM) x 730 Hours (Pay as you go), Windows (AHB), OS Only | $1,471.68              |
|                                            |         |                                                              | **$4,824.29**          |

Migration costs include the one-time expenses for migrating databases, applications, and data using cloud migration services. Here is a detailed breakdown:

- **Azure Migrate**: No charge.
  - **Reason**: Azure Migrate provides a centralized hub to assess and migrate on-premises servers, infrastructure, applications, and data to Azure. It simplifies the migration process and ensures a smooth transition with minimal downtime.
- **Azure Database Migration Service**: $449.68/month for database migration, configured with 4 vCores, 2 instances, running 730 hours per month.
  - **Reason**: This service facilitates seamless database migrations with minimal downtime. It supports both homogeneous (e.g., SQL Server to Azure SQL Database) and heterogeneous (e.g., MySQL to Azure SQL Database) migrations, ensuring data integrity and continuity.
- **Network Bandwidth**: $2,582.40/month for 30,720 GB outbound data transfer.
  - **Reason**: Adequate bandwidth is essential for transferring large volumes of data during the migration process. This ensures that data is moved efficiently and securely without bottlenecks.
- **Storage Accounts**: $320.532/month for 15 TB capacity, LRS redundancy, hot access tier.
  - **Reason**: Azure Storage Accounts provide scalable and secure storage solutions for data migration. The hot access tier is optimized for data that is accessed frequently, ensuring quick retrieval times during and after migration.

### Operational Costs

| **Service type**           | **Custom name**               | **Region**  | **Description**                                              | **Estimated monthly cost** |
| -------------------------- | ----------------------------- | ----------- | ------------------------------------------------------------ | -------------------------- |
| Virtual Machine Scale Sets | West US Web Front-End Cluster | West US     | 10 D2 v3 (2 vCPUs, 8 GB RAM) (3 year savings plan), Windows (AHB), OS Only | $401.43                    |
| Virtual Machine Scale Sets | Asia Web Front-End Cluster    | East Asia   | 10 D2 v3 (2 vCPUs, 8 GB RAM) (3 year savings plan), Windows (AHB), OS Only | $529.98                    |
| Virtual Machine Scale Sets | Europe Web Front-End Cluster  | West Europe | 10 D2 v3 (2 vCPUs, 8 GB RAM) (3 year savings plan), Windows (AHB), OS Only | $481.80                    |
| Azure SQL Database         | Primary Database              | East US     | Elastic Pool, vCore, Business Critical, Provisioned, Standard-series (Gen 5), 5 - 4 vCore Pool(s) x 730 Hours, 1024 GB Storage, SQL License (AHB), RA-GRS Backup Storage Redundancy, 0 GB Point-In-Time Restore,  1 x 5,000 GB Long Term Retention | $6,358.75                  |
| Azure Cosmos DB            | NoSQL                         | East US     | Azure Cosmos DB for NoSQL (formerly Core), Standard provisioned throughput (manual), Always-free quantity disabled, Pay as you go, Single Region Write (Single-Master) - East US (Availability Zones enabled) (Write Region), 10,000 RU/s x 730 Hours, 10,240 GB transactional storage, Analytical storage disabled, 2 copies of periodic backup storage, Dedicated Gateway not enabled | $3,290.00                  |
| Storage Accounts           | Data Warehouse                | East US     | Block Blob Storage, General Purpose V2, Flat Namespace, GRS Redundancy, Hot Access Tier, 15 TB Capacity - Pay as you go, 10 x 10,000 Write operations, 10 x 10,000 List and Create Container Operations, 10 x 10,000 Read operations, 1 x 10,000 Other operations. 1,000 GB Data Retrieval, 1,000 GB Data Write, SFTP disabled, 1000 GB Geo-replication data transfer | $725.53                    |
| Content Delivery Network   |                               |             | Zone 1: 0 TB, Zone 2: 0 GB, Zone 3: 0 GB, Zone 4: 0 GB, Zone 5: 0 GB, DSA: 3 TB | $543.74                    |
| Load Balancer              |                               | East US     | Standard Tier: 5 Rules, 5 TB Data Processed                  | $43.85                     |
| Virtual Machines           | GPU                           | East US     | 1 NC40ads H100 v5 (40 vCPUs, 320 GB RAM) (3 year savings plan), Windows (AHB), OS Only; 0 managed disks – S4; Inter Region transfer type, 5 GB outbound data transfer from East US to East Asia | $3,143.35                  |
| Bandwidth                  |                               |             | Internet egress, 5120 GB outbound data transfer from West US routed via Microsoft Global Network | $436.74                    |
|                            |                               |             |                                                              | **$15,955.17**             |

Operational costs include the monthly expenses for running virtual machines, databases, load balancers, storage, and network across multiple regions. Here is a detailed breakdown:

- **Virtual Machines**:
  - **North America**: $1,471.68/month for 21 D2 v3 instances (2 vCPUs, 8 GB RAM), running 730 hours per month.
  - **Asia-Pacific**: $529.98/month for 10 D2 v3 instances (2 vCPUs, 8 GB RAM), on a three-year savings plan.
  - **Europe**: $481.80/month for 10 D2 v3 instances (2 vCPUs, 8 GB RAM), on a three-year savings plan.
  - **Reason**: Virtual machines provide the necessary compute power to run applications and services. Using a mix of regions ensures global availability and low latency for users in different geographic locations.
- **Load Balancer**: $43.85/month for standard tier, 5 rules, processing 5 TB of data.
  - **Reason**: Load balancers distribute incoming network traffic across multiple virtual machines, ensuring high availability and reliability of applications. This helps prevent any single VM from becoming a bottleneck.
- **Content Delivery Network (CDN)**: $543.744/month for 3 TB of data transfer.
  - **Reason**: Azure CDN accelerates the delivery of web content by caching it at strategically placed locations around the world. This reduces latency and improves user experience by delivering content faster.
- **Azure SQL Database**: $6,358.751/month for a 5 TB primary database, elastic pool, business critical, standard series (Gen 5), RA-GRS backup storage redundancy.
  - **Reason**: Azure SQL Database provides a fully managed relational database service with built-in high availability, scalability, and security. The business critical tier ensures high performance and resilience for mission-critical applications.
- **Azure Cosmos DB**: $3,290/month for a 10 TB NoSQL database, standard provisioned throughput, single region write, availability zones enabled.
  - **Reason**: Azure Cosmos DB offers a globally distributed, multi-model database service with low latency and high availability. It is ideal for applications that require fast and scalable access to large volumes of data.
- **Data Warehouse**: $725.532/month for 15 TB capacity, GRS redundancy, hot access tier.
  - **Reason**: Azure Storage Accounts for data warehousing provide scalable and secure storage solutions for large datasets. The GRS redundancy ensures data durability and availability across different geographic regions.
- **GPU Virtual Machine**: $3,143.3508/month for 1 NC40ads H100 v5 instance (40 vCPUs, 320 GB RAM), on a three-year savings plan.
  - **Reason**: GPU virtual machines are essential for machine learning and data processing tasks that require high computational power. They accelerate the training and inference of ML models, improving efficiency and performance.
- **Network Bandwidth**: $436.74/month for 5,120 GB outbound data transfer.
  - **Reason**: Sufficient network bandwidth is necessary to handle the ongoing data transfer needs of the operational environment, ensuring smooth and uninterrupted service delivery.

### Management Costs

| **Service type**          | **Custom name** | **Region** | **Description**                                              | **Estimated monthly cost** |
| ------------------------- | --------------- | ---------- | ------------------------------------------------------------ | -------------------------- |
| Microsoft Cost Management |                 |            | No charge for managed Azure spend. 0 Managed AWS spend per month | $0.00                      |
| Azure Managed Grafana     |                 | East US    | Standard pricing plan, 730 Hours, zone redundancy added, 0 active users | $79.94                     |
| Azure Monitor             |                 | East US    | Log analytics: Log Data Ingestion: 10 GB Daily Auxiliary logs, 10 GB Daily Basic logs, 2 GB Daily Analytics logs ingested, 1 months of Interactive Retention, 0 months of Retention, 100 GB data restored for 30 days, 0 queries per day with 0 GB data scanned per query, 0 GB of Log Data Exported per day, Platform Log Data Processed per day: 0 GB with Destination to Storage or Event Hub and 0 GB with Destination to Marketplace Partners, 0 Search job Queries per day with 0 GB data scanned per query; 1 SCOM MI Endpoints; Managed Prometheus: 0 AKS nodes in cluster, 10000 Prometheus metrics per node, 30 seconds of Metric collection interval, 0 Average daily Dashboards users, 7 Dashboards, 50000 Data samples queried per dashboard, 25 promql alerting rules, 25 promql recording rules; Application Insights: 0 GB Daily Analytics logs ingested, 3 months Data retention, 0 Standard Web Tests, 5 Minutes Execution frequency, Executing for 730 hours; 0 resources monitored X 1 metric time-series monitored per resource, 5 Minutes Log Signal frequency with 0 log signals monitored and 1 time series per signal, 0 Additional events (in thousands), 10 Additional emails (in 100 thousands), 10 Additional push notifications (in 100 thousands), 10 Additional web hooks (in millions) | $658.50                    |
|                           |                 |            |                                                              | **$738.44**                |

Management costs include expenses for cost management, monitoring, logging, and security management tools. Here is a detailed breakdown:

- **Microsoft Cost Management**: No charge.
  - **Reason**: Microsoft Cost Management helps organizations monitor, allocate, and optimize their cloud spending. It provides insights into cost drivers and helps in budgeting and forecasting.
- **Azure Managed Grafana**: $79.935/month for the standard pricing plan, with zone redundancy enabled.
  - **Reason**: Azure Managed Grafana provides powerful data visualization and monitoring capabilities. It helps in tracking system performance, identifying issues, and ensuring the health of the infrastructure.
- **Azure Monitor**: $658.5/month for log analytics, including 10 GB daily auxiliary logs, 10 GB daily basic logs, 2 GB daily analytics logs, and 1 month of interactive retention.
  - **Reason**: Azure Monitor offers comprehensive monitoring and diagnostics for applications and infrastructure. It helps in collecting, analyzing, and acting on telemetry data from Azure and on-premises environments.

## Cost Optimization Strategies

To reduce costs, ShopPro International can consider the following strategies:

1. **Reserved Instances**: Using reserved instances instead of on-demand instances can significantly lower the cost of compute resources. For example, a three-year reserved instance plan can save a substantial amount.
2. **Autoscaling**: Configure autoscaling to dynamically adjust resources based on demand, optimizing costs during peak and off-peak periods.
3. **Hybrid Benefits**: Utilize Azure Hybrid Benefits to use existing Windows Server and SQL Server licenses, reducing licensing costs.
4. **Serverless Services**: Consider using serverless computing services like Azure Functions and Logic Apps to minimize unnecessary compute resource usage.

## Future Growth and Budget Planning

Costs are expected to increase over the next three years to accommodate business growth. Here is a detailed forecast and optimization suggestions:

#### Year 1

- **Estimated Cost**: $15,955.1748/month.
- Optimization Suggestions
  - **Reserved Instances**: Start using reserved instances, especially for long-running virtual machines and database instances.
  - **Autoscaling**: Implement autoscaling policies to dynamically adjust resources based on actual demand, avoiding unnecessary expenses.
  - **Hybrid Benefits**: Leverage existing Windows Server and SQL Server licenses to reduce licensing costs.

#### Year 2

- **Estimated Cost**: $17,550/month (assuming 10% business growth).
- Optimization Suggestions
  - **Evaluate New Instance Types**: As Azure introduces new instance types, evaluate and migrate to more efficient instance types to further optimize costs.
  - **Serverless Services**: Gradually introduce serverless computing services like Azure Functions and Logic Apps to reduce fixed compute resource usage.
  - **Cost Monitoring**: Use Azure Cost Management tools to continuously monitor and analyze costs, identifying potential optimization opportunities.

#### Year 3

- **Estimated Cost**: $19,305/month (assuming 10% business growth).
- Optimization Suggestions
  - **Continuous Optimization**: Continuously optimize resource configurations based on business needs and technological advancements to ensure costs remain within budget.
  - **New Technology Adoption**: Adopt new Azure services and technologies, such as serverless databases and AI services, to improve efficiency and reduce costs.
  - **Long-term Planning**: Develop a long-term cost management and optimization strategy to ensure future cost growth is controlled and supports ongoing business expansion.
