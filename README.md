# `AWS_AutoScaling-Project`
The project is implemented to ensure the consistent availability of the application

# `REQUIREMENTS:`
AWS Account :
a. Launch Template

b. Elastic Loadbalancer

c. Target-group

d. Elastic Autoscaling

# `Introduction:`
In today's dynamic digital landscape, ensuring the availability and reliability of applications is paramount. To meet this demand, my project focuses on leveraging AWS autoscaling and load balancing capabilities to maintain consistent availability of our application.

# `Launch Template:`
A launch template is a powerful tool provided by AWS to simplify the process of launching instances within an autoscaling group. It serves as a blueprint for configuring the launch parameters of EC2 instances, such as instance type, AMI (Amazon Machine Image), security groups, storage, and networking settings.

# `Target Group:`
A target group is a fundamental component of the AWS Application Load Balancer (ALB) and Network Load Balancer (NLB) services. It serves as a logical grouping of targets, such as EC2 instances, IP addresses, or Lambda functions, that receive incoming traffic from the load balancer.

# `Load Balancer:`
A load balancer acts as a traffic distributor, evenly distributing incoming requests across multiple instances of our application. AWS offers various types of load balancers, including Application Load Balancer (ALB) and Network Load Balancer (NLB), each suited for different use cases. By deploying a load balancer in front of our application instances, we achieve high availability and fault tolerance, as well as improved scalability and security.

# `Autoscaling:`
Autoscaling is a crucial feature provided by AWS that automatically adjusts the number of instances in a computing group based on the demand. By configuring autoscaling policies, we ensure that our application can seamlessly handle fluctuations in traffic without manual intervention. This not only improves performance but also optimizes costs by scaling resources up or down as needed.

# `Integration and Configuration:`
Integrating autoscaling with load balancing in AWS involves configuring autoscaling groups and attaching them to the load balancer. This ensures that new instances launched by autoscaling are automatically registered with the load balancer, seamlessly expanding the capacity of our application to handle increased traffic.

# `Creation of Launch Template:`
Enter the name of the launch template.

Enter the description as the purpose of creation of launch tempalate

![Screenshot 2024-09-18 122541 1](https://github.com/user-attachments/assets/3c7690ed-d00d-4737-89bc-98b3fe0856bf)

Select the amazon machine image "AMI"
![Screenshot 2024-09-18 122615 2](https://github.com/user-attachments/assets/8d32b6dd-7fb0-4f55-ad4e-ced8ed9c4f1b)

Select the instance type here i used "t2.micro".

Select the keypair.
![Screenshot 2024-09-18 122653 3](https://github.com/user-attachments/assets/e8cc3d00-0d9a-4196-b4b8-c34ff56fc435)

Configure the network settings:

Here i used default subnet-id and selected the existing security-group.
![Screenshot 2024-09-18 122843 4](https://github.com/user-attachments/assets/edef9637-aa32-4447-ac6d-d87dd85974fb)

The launch template is created successfully.
![Screenshot 2024-09-18 123403 5](https://github.com/user-attachments/assets/83b264f1-eef2-45b7-94a4-1d499f5ec314)

# `Ceation of Target-Group:`
Create a Target-Group.
![Screenshot 2024-09-18 123517 6](https://github.com/user-attachments/assets/84cc5004-22af-405f-ac9e-3908fb1bb7d5)

Enter the name of the target-group.

Enter the protocol:port as http:80

Enter the type of ip-address as : IPv4

Select the vpc
![Screenshot 2024-09-18 123625 7](https://github.com/user-attachments/assets/44d7bf91-b406-4976-8554-a75108f10f6f)

Enter the path of the health checkuo here i used : /health
![Screenshot 2024-09-18 123730 8](https://github.com/user-attachments/assets/96a9dc1d-5ec5-4f38-8577-a3d51e3fda8c)

The Target-Group is created successfully.
![Screenshot 2024-09-18 123838 9](https://github.com/user-attachments/assets/ea457160-7970-4908-aaa1-c8e856f55ae7)

# `Creation of LoadBalancer:`

Select the Application Loadbalancer.
![Screenshot 2024-09-18 123906 10](https://github.com/user-attachments/assets/b909fb73-ceee-482d-ac72-da25ceb2112c)

Enter the name of the load-balancer

select the scheme: as internal-facing

select the ip-address type as : IPv4
![Screenshot 2024-09-18 124012 11](https://github.com/user-attachments/assets/3f783787-3819-4022-ba35-e8b8a562712f)

Configure the network mapping :

Select the Availability zones for the vpc
![Screenshot 2024-09-18 124055 12](https://github.com/user-attachments/assets/dfcc3726-d2a2-4ceb-8055-670522ecbcb6)

Add the target-group
![Screenshot 2024-09-18 124148 13](https://github.com/user-attachments/assets/1482fd0e-910e-4d12-b206-dd0207eaf3e8)

Load-balancer is created successfully.
![Screenshot 2024-09-18 124232 14](https://github.com/user-attachments/assets/3424edfd-92b4-424b-86a0-a5beadec9da4)

# `Creation of Auto-Scaling:`
Select the launch template.
![Screenshot 2024-09-18 124700 15](https://github.com/user-attachments/assets/d7199888-fd45-45b2-8ee6-c9e897849a1d)

Select the availability-zones.
![Screenshot 2024-09-18 134332 16](https://github.com/user-attachments/assets/fa019293-a56f-4989-8406-5b96c67c5fac)

Attach the load-balancer
![Screenshot 2024-09-18 134418 17](https://github.com/user-attachments/assets/84ee7ea0-3b05-4237-bd81-db72396414b7)
![Screenshot 2024-09-18 134506 18](https://github.com/user-attachments/assets/52dc8f70-295f-4976-97f0-4ab0de439354)

Enter the desired capacity for instances.
![Screenshot 2024-09-18 134552 19](https://github.com/user-attachments/assets/a2cd370a-f4b5-4021-b7f0-806cf6424601)

Enter the minimum and maximum capacity for the instances

here i choose min=1,max=5

Select the scaling target policy as cpu-utilization
![Screenshot 2024-09-18 134700 20](https://github.com/user-attachments/assets/fce931d7-863a-4c22-8eb0-27ea29f51455)

Then select the cpu limit as 50% for scaling the instance.
![Screenshot 2024-09-18 134804 21](https://github.com/user-attachments/assets/57fb50e1-eb2f-4162-92d4-376dafdd6857)

Add the notification : E-mail

You can get notification for every launching and termination of instances
![Screenshot 2024-09-18 134859 22](https://github.com/user-attachments/assets/bb8ad646-62e2-4852-a354-323497d31a67)

The auto-scaling-group is created successfully.
![Screenshot 2024-09-18 192549 23](https://github.com/user-attachments/assets/185852b6-071b-4610-8f50-fba393cc6d64)

The instance is initialized by the elastic-autoscaling-group
![Screenshot 2024-09-19 114603 24](https://github.com/user-attachments/assets/e3680954-a37d-488e-b993-435d8a5a8e0b)

I connected to the instance and installed the stress in it.

The stress is a artificial load increser which increases the cpu-utilization than we can see the auto-scaling process in live.

we can have to enter the command : stress -c "percentage of cpu-utilization you want to increase" .

command : stress -c 400
![Screenshot 2024-09-18 200039 25](https://github.com/user-attachments/assets/95c81e0f-2c80-4342-9af2-466ab1a3040c)

The cpu-utilization increased

alt text

I got notification for launching of new instance

alt text alt text

I have successfully implemented the autocaling project

alt text

# `Conclusion:`
By harnessing the power of AWS autoscaling and load balancing, I've successfully enhanced the availability, scalability, and reliability of our application. In real-time This ensures a seamless user experience even during periods of high demand, ultimately driving customer satisfaction and business success.

# `The project is completed.`
