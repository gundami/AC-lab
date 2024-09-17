# **Migration Requirements Gathering**

> Fujitsu's ERP, GLOVIA, Now Migratable to Azure or Newly Introduced on Azure. Connects to Cloud Services, Aims to Resolve 2025 Digital Cliff

## Why to migrate? 

One of the reasons why Fujitsu migrate GLOVIA to Azure was because the environment surrounding accounting operation is changing significantly. In previous years, the major premise was that the core system operated on-premises. However, the number of customers who choose the cloud when new to choose this system or migrating to the new system is increasing significantly. Only a small number of customers will choose to operated on-premises. 70%-80%of customers will choose to premise on cloud.

At the same time, there is an increasing demand from customers to use those distinctive functions on the Azure platform. Many customers hope to use GLOVIA within the same system environment. For example, a shipbuilding company plans to migrate GLOVIA on its on-premises virtual   platform Windows Server to Azure to obtain continued support.

## Questions to ask for more about company infrastructure? 

1. What are Fujitsu's operations that help standardization and advancement of GLOVIA software, and how does it achieve flexible customization?

2. What are the differences between GLOVIA software based on the deployment of IaaS and SaaS?

3. How is the mechanism for unified financial accounting and management accounting management?

## RACI matrix 

| Task                                     | **Responsible** (R)            | **Consulted** (C) | **Accountable** (A)            | **Informed** (I) |
| ---------------------------------------- | ------------------------------ | ----------------- | ------------------------------ | ---------------- |
| Cloud Migration Strategy Development     | IT Team                        | Business Team     | CIO                            | All Teams        |
| Safety and compliance                    | Safety Team                    | Legal Team        | Safety Team                    | Operation Team   |
| Data Migration                           | Data Team                      | IT Team           | Project Manager                | Development Team |
| Application Migration                    | Development Team               | IT Team           | Development Team               | Business Team    |
| Performance surveillance after migration | operation and maintenance team | IT Team           | operation and maintenance team | All Teams        |

## The most suitible migration approach

For GLOVIA, I think SaaS is the most suitable way to migrate. Because SaaS services can provide standardized services, most companies only need universal standard functions. The customer's system consists of multiple components, such as sales management to manufacturing and cost settlement. The data obtained from these components must be collected into GLOVIA. Using Saas technology can help integrate other products of the company, and can link other products and accounting systems as highlights as highlights to customers. It can also reduce the cost of customers' development of supporting systems. SaaS services can also make GLOVIA out of the box.

Based on IaaS deployment, users need to spend more money on infrastructure. If it is not a big company, it will not require customized functions. This is undoubtedly a waste of resources.

## High level schedule for the migration process

I divide the migration process into three items. The first step is to rearchitect the system before the migration, upgrading the software into a suitable SaaS deployment. For example, a system that is deployed under IaaS, the SaaS system needs to add the function of new customer management and isolation of customer data. The second step is to deploy. This step needs to be deployed on the server. It also ensures that the service is scalable to adapt to the situation that the subsequent business capacity needs to be increased or decreased. The third step is data migration. Customers need to migrate the data on the original system to the SaaS platform. Since then, the customer can seamlessly migrate to the new SaaS system.

## Main decision criteria for the company

I think the company's main decision depends on the number of customers who require SaaS based GLOVIA. Only when most customers choose SaaS, which are more companies that do not need special processes, migrating GLOVIA to the SaaS platform is a feasible option. This is due to cost considerations.