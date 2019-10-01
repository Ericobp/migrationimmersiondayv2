# AWS Application Discovery Service & Migration Hub Lab

---

© 2020 Amazon Web Services, Inc. and its affiliates. All rights reserved. This work may not be reproduced or redistributed, in whole or in part, without prior written permission from Amazon Web Services, Inc. Commercial copying, lending, or selling is prohibited.

Errors or corrections? Email us at onpremsimulator@amazon.com.

## Lab Overview

This lab will walk you through the installation and configuration of [AWS Application Discovery Service](https://aws.amazon.com/application-discovery/) (ADS) agents on the VMs and start its data collection. As part of this lab, [Amazon Athena](https://aws.amazon.com/athena/) is also going to be used to understand the current environment and the relationship between servers and applications stacks. The information collected on ADS is going to be used as input in [AWS Migration HUB](https://aws.amazon.com/migration-hub/) (HUB) as the initial application grouping and definition of migration waves.

This lab demonstrates how to:

- Install ADS agents on Linux and Windows
- Have insights from your environment using Amazon Athena
- Group Servers as Applications using Migration Hub

## ADS Overview

The AWS Discovery Agent is AWS software that you install on on-premises servers and VMs targeted for discovery and migration. Agents capture system configuration, system performance, running processes, and details of the network connections between systems. Agents support most Linux and Windows operating systems, and you can deploy them on physical on-premises servers, Amazon EC2 instances, and virtual machines.

The Discovery Agent runs in your local environment and requires root privileges. When you start the Discovery Agent, it registers with the Application Discovery Service endpoint, arsenal.aws.com, and pings the service at 15 minute intervals for configuration information. When you send a command that tells an agent to start data collection, it starts collecting data for the host or VM where it resides. Collection includes system specifications, times series utilization or performance data, network connections, and process data. You can use this information to map your IT assets and their network dependencies. All of these data points can help you determine the cost of running these servers in AWS and also plan for migration.

Data is transmitted securely by the Discovery Agents to Application Discovery Service using Transport Layer Security (TLS) encryption. Agents are configured to upgrade automatically when new versions become available. You can change this configuration setting if desired.

&nbsp;

# Required information to execute this LAB

You will also need to get familiar with the servers to be migrated:

| Application | Software | Server Name | OS | IP Address | Username | Password | Application Test |
| --- | --- | --- | --- | --- | --- | --- | --- |
| WordPress blog | Apache/PHP | MID-Wordpress-WEB | Linux | 192.168.1.218 | user | Password you defined during CloudFormation | http://wordpress-web/ |
|  | MySQL | MID-Wordpress-DB | Linux | 192.168.1.247 | user | Password you defined during CloudFormation |   |
| OFBiz ERP | Apache/Java | MID-OFBiz-WEB | Linux | 192.168.1.84 | user | Password you defined during CloudFormation | https://ofbiz-web:8443/accounting |
|  | Postgre SQL | MID-OFBiz-DB | Linux | 192.168.1.194 | user | Password you defined during CloudFormation |   |

&nbsp;

⭐Tips

💡 You can use the EC2 Bastion host to login into the WordPress and OFBiz servers.

💡 The EC2 Bastion host has SSH to login into the WordPress and OFBiz applications. Just go to the Windows Command Prompt and type "ssh user@IP_Address"



## [Next](./1_know_your_environment.md)

✅ Proceed to the first part, [know your environment](./README_ADS_MD/1_know_your_environment.md), wherein you'll connect to the source environment to be discovered.

&nbsp;
