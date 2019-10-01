# AWS Application Discovery Service & Migration Hub Lab


---

© 2020 Amazon Web Services, Inc. and its affiliates. All rights reserved. This work may not be reproduced or redistributed, in whole or in part, without prior written permission from Amazon Web Services, Inc. Commercial copying, lending, or selling is prohibited.

Errors or corrections? Email us at onpremsimulator@amazon.com.


# Know your environment

In this exercise, you perform the following tasks:

- Know the servers
- Test if existing applications are working

&nbsp;

✅ Step-by-step Instructions

### Connect to the AWS Console


**1.** [Click here to go to the EC2 Console](https://us-west-2.console.aws.amazon.com/ec2/v2/home?region=us-west-2#Instances:sort=tag:Name)

**2.** Make sure that there are EC2 instances in your environment, and those isntances are with ‘Running’ state.

**3.** Once connected to the MID-Bastion server, test if the applications are working.

To test the application, Open Chrome in the MID-Bastion host and connect to the 2 application servers as per defined bellow:

| Application  | Application URL       |
| ---          | ---                   |
| WordPress    | http://wordpress-web/ |
| OFBiz  | https://ofbiz-web:8443/accounting |

You should be able to open the Migration Immersion Day Wordpress blog and a OFBiz ERP management page.

&nbsp;

⭐Tips

💡 You can use Remote Desktop to access the EC2 Bastion host and then login into the WordPress and OFBiz servers via SSH.

💡 Since this lab simulates a migration from a production environment to AWS, you should only connect to the application servers using the Bastion host.

&nbsp;

## [Next](./2_create_iam_credentials.md)

✅ Proceed to the next step, [create ADS user](./2_create_iam_credentials.md), wherein you'll create the IAM user that will be used by ADS agents.

&nbsp;
