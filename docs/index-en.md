# Community Edition Redis Service Instance Deployment Document
## Overview
Redis is a high performance HTTP and reverse proxy server. apsaradb for redis provides the community edition service on the computing nest. you can quickly deploy apsaradb for redis services on the computing nest and implement o & amp; m monitoring without having to configure your own cloud host, so that you can easily build your own applications based on apsaradb for redis. this topic describes how to activate the redis community edition service on the computing nest, as well as the deployment process and usage instructions.
## Billing Description
The cost of the redis community edition on the computing nest mainly involves:

-Selected vCPU and memory specifications
-Disk capacity
-Public network bandwidth

Billing methods include:

-Pay-as-you-go (hourly)
-Annual and monthly packages

The estimated cost is displayed in real time when you create an instance.

## Deployment Architecture
the community edition of redis is deployed on a single machine.

## Required Permissions for RAM Users
The Redis service needs to access and create resources such as ECS and VPC. If you use a RAM user to create a service instance, you need to add the corresponding resource permissions to the account of the RAM user before creating the service instance. For detailed instructions on adding RAM permissions, see [Grant Permissions to RAM Users](https://help.aliyun.com/document_detail/121945.html). The required permissions are shown in the table below.

| Permission policy name | Comment |
| --- | --- |
| AliyunECSFullAccess | Permissions to manage ECS instances |
| AliyunVPCFullAccess | Permissions to manage a VPC |
| AliyunROSFullAccess | Manage permissions for Resource Orchestration Service (ROS) |
| AliyunComputeNestUserFullAccess | Manage user-side permissions for the compute nest service (ComputeNest) |
| AliyunCloudMonitorFullAccess | Permissions to manage CloudMonitor |


## Deployment process
### Deployment Steps
Click [Deployment Link](https://computenest.console.aliyun.com/user/cn-hangzhou/serviceInstanceCreate?ServiceId=service-393b398bccc1459e93fc) to go to the service instance deployment page. Follow the on-screen instructions to fill in the parameters and complete the deployment.


### Deployment Parameter Description
During the process of creating a service instance, you need to configure the service instance information. the following section describes the input parameters of the community redis service instance.

| Parameter Group | Parameter Item | Example | Description |
| ------------ | --------- | --- | ----------------------------------------------------------------------- |
| Service Instance Name | | test | The name of the instance |
| Region | | China East 1 (Hangzhou) | The region of the selected service instance. We recommend choosing the region closest to you for lower network latency. |
| Availability Zone Configuration | Deployment Region | Availability Zone I | Different availability zones within a region |
| Payment Type Configuration | Payment Type | Pay-As-You-Go or Subscription |
| Select Existing Infrastructure Configuration | VPC ID | vpc-xxx | Select the ID of the VPC. |
| Select Existing Infrastructure Resources | VSwitch ID | vsw-xxx | Select a VSwitch ID. If the switch cannot be found, try switching the region and availability zone.
| ECS Instance Configuration | Instance Type | ecs.g7.large | Instance specifications can be selected based on actual needs |
| ECS Instance Configuration | System Disk Space | 40 | System disk space can be selected based on actual requirements |
| ECS Instance Configuration | Data Disk Space | 40 | Data disk space; can be selected based on actual needs |
| ECS Instance Configuration | Instance Password | ******** | Set the instance password. The password must be 8 to 30 characters long and include at least three of the following: uppercase letters, lowercase letters, numbers, and special characters from the set: ()'~!@#$%^&*-+={}[]:;'<>,.?/. |
| ECS Instance Configuration | Enable Public IP | true | Whether to enable a public IP address |
| Redis Configuration | Redis Password | ******** | The password must contain 8 to 30 characters and must contain at least three of uppercase letters, lowercase letters, numbers, and special characters., Length 8-30, must contain three items (uppercase letters, lowercase letters, numbers, ()'~!@#$%^& *_-+ ={}[]:;' <>,.?/special symbols) |

![1.jpg](images-en/1.jpg)


### Verification Results

1. View the service instance.
After the service instance is created, the deployment will take approximately 2 minutes. After deployment is complete, you can see the corresponding service instances on the page.

![2.jpg](images-en/2.jpg)

2. Access redis through the service instance.

![3.jpg](images-en/3.jpg)
After entering the corresponding service instance, you can obtain the PublicEndpoint, PrivateEndpoint, and InstallPath on the page.


### Using Redis
Please visit the redis official website to learn how to use redis:[redis usage document](https://redis.io/docs/)
