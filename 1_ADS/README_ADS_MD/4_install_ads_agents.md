# AWS Application Discovery Service & Migration Hub Lab


---

© 2020 Amazon Web Services, Inc. and its affiliates. All rights reserved. This work may not be reproduced or redistributed, in whole or in part, without prior written permission from Amazon Web Services, Inc. Commercial copying, lending, or selling is prohibited.

Errors or corrections? Email us at onpremsimulator@amazon.com.


# Install ADS agents to the VMs

In this exercise, we will:

- Install ADS agents to the VMs
- Start the data collection in AWS ADS console.

&nbsp;

✅ **Step-by-step directions**

**1.** From the EC2 Console, connect to each instance from the list bellow. 

⭐️ Tips

💡 For Linux VMs, Putty or SSH should be used and for Windows VMs Remote Desktop. Both  are available in your Bastion Host.



 Application | Software | Server Name | OS | IP Address | Username | Password | Application Test |
| --- | --- | --- | --- | --- | --- | --- | --- |
| WordPress blog | Apache/PHP | MID-Wordpress-WEB | Linux | 192.168.1.218 | user | Password you defined during CloudFormation | http://wordpress-web/ |
|  | MySQL | MID-Wordpress-DB | Linux | 192.168.1.247 | user | Password you defined during CloudFormation |   |
| OFBiz ERP | Apache/Java | MID-OFBiz-WEB | Linux | 192.168.1.84 | user | Password you defined during CloudFormation | https://ofbiz-web:8443/accounting |
|  | Postgre SQL | MID-OFBiz-DB | Linux | 192.168.1.194 | user | Password you defined during CloudFormation |   |


**2.** Download and install the agents as per the following instructions:

⭐️ Tips

💡 Replace < AWS key id > and < AWS key secret > with the information downloaded during the ADS user key creation step.

💡 Copy the commands below to notepad and replace the < AWS key id > and < AWS key secret > values.

&nbsp;

*Linux*:

```BASH
curl -o ./aws-discovery-agent.tar.gz https://s3-us-west-2.amazonaws.com/aws-discovery-agent.us-west-2/linux/latest/aws-discovery-agent.tar.gz
tar -xzf aws-discovery-agent.tar.gz
sudo bash install -r us-west-2 -k <AWS key id> -s <AWS key secret>
```
⭐️ Tip: each line is an individual command to be executed.

&nbsp;


*Windows*:

Open Powershell:

```POWERSHELL
Import-Module BitsTransfer
Start-BitsTransfer -Source "https://s3-us-west-2.amazonaws.com/aws-discovery-agent.us-west-2/windows/latest/AWSDiscoveryAgentInstaller.msi" -Destination "C:\Users\Administrator\Downloads\"
msiexec.exe /i c:\Users\Administrator\Downloads\AWSDiscoveryAgentInstaller.msi REGION="us-west-2" KEY_ID="<aws key id>" KEY_SECRET="<aws key secret>" /q
```
⭐️ Tip: each line is an individual command to be executed.

&nbsp;

**4.** Repeat the steps until all Linux and Windows instances have the agent installed.

&nbsp;

## [Next](.././README_ADS_MD/5_start_data_collection.md)

✅ Proceed to the next step, [start data collection](.././README_ADS_MD/5_start_data_collection.md), wherein you'll enable ADS to start collecting data from the ADS agents.

&nbsp;
