# **Concepts & Tools:**
- in this project we will be hosting our apllication in a two-tier architecture (internet-facing-app & secure Database)
- **AWS** for infrastrutre
- **Jenkins** for automation
- **github** as remote repository hold our latest/most recently updated version of application
- **mongodb** for database

# **Project Overview:**
- Any contibution/update made to the application and pushed to github will be automatically deployed to the servers running the application
- IT mean the customers using the application over the intenet will be able to see and experience any of the changes.
- changes can be made by any developer, it will be checked(tested) and merged with the overall project and the new updated version of the overall project will be deployed on AWS infrastructure
![](pics/overall_flow.png)
# **AWS Overview**
>  **VPC** will be created
>>  4 **subnets** will be created inside the VPC:
 - Public_subnet
 -  - Machines hosted in this subnet will be accessible from the intenet directly
 - Private_subnet
 - - Machines hosted in this subnet will not be accesable from the internet
 - - however we will provide a **Nat-Insatnce** so that the machines can acess the intenet(in case they need to perform any software updates)
 - Jenkins_subnet
 - Bastion_subnet 
>> Each subnet will be attached to **Routing-Table** made for them:
- - public_subnet : **public_RT**
- - private_subnet : **private_RT**
- - Jenkins-subnet : **jenkins_RT**
- - Bastion_subnet : **bastion_RT**

>>>> Type of Instances(EC2):
- Public_subnet:
-    1. Internet-facing web app
-  2. Nat-Insance
- Private_subnet:
-  3. Database
- Jenkins_subnet:
-  4. EC2 running the Jenkins
- Bastion_subnet:
-  5. Bastion Ec2
>>>> Security_group_ec2
1. Internet-Facing app:
- - ssh from local machine
- - access to port 3000(this is where the applicaion is running)
2. Nat_Insatnce
- - ssh from local machine
- - 

