# migrationimmersiondayv2
Temporary placeholder - will be migrate later to another repository - 

Placeholder for the cloudformation that creates the source environment to be migrated

Launch the cloudformation using the MASTER.json with the S3 URL bellow. It will invoke the cloudformation stacks in the correct order to launch the source environment to be migrated.

[S3 URL](https://midsourceenv.s3.amazonaws.com/migrationimmersiondayv2/0_Source_environment/MASTER.json)

**MASTER** -> ROOT for clouformation. Invokes SOURCE_NETWORK, SOURCE_BASTION, SOURCE_NOPCOMMERCE, SOURCE_WORDPRESS in the right order

**SOURCE_NETWORK** -> Creates a VPC, 2 subnets (public+private), routing tables, NAT and a Linux box with BIND/NAMED configured as Dynamic DNS server. It also changes the VPC's DHCP option to resolv using the Linux DNS server instead of the VPC resolver. All the other servers in the stack MUST include the step to register in the Linux DNS server.

**SOURCE_BASTION** -> Windows Bastion with some tools pre-installed. Should be launched in the PUBLIC Subnet. It is the only entry point for external connection. All other servers must be launched in the private network. Current version installs putty, Firefox, python.

**SOURCE_NOPCOMMERCE** -> 2 stack Windows (.NET Core + SQLServer) running NOPCOMMERCE. Launch in the PRIVATE network

**SOURCE_WORDPRESS** -> 2 stack Linux (PHP + mariaDB) running Wordpress. Launch in the PRIVATE network
