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

alt text

Select the amazon machine image "AMI"

alt text

Select the instance type here i used "t2.micro".

Select the keypair.

alt text

Configure the network settings:

Here i used default subnet-id and selected the existing security-group.

alt text

The launch template is created successfully.

alt text

# `Ceation of Target-Group:`
Create a Target-Group.

alt text

Enter the name of the target-group.

Enter the protocol:port as http:80

Enter the type of ip-address as : IPv4

Select the vpc

alt text

Enter the path of the health checkuo here i used : /health

alt text

The Target-Group is created successfully.

alt text

# `Creation of LoadBalancer:`
Select the Application Loadbalancer.

alt text

Enter the name of the load-balancer

select the scheme: as internal-facing

select the ip-address type as : IPv4

alt text

Configure the network mapping :

Select the Availability zones for the vpc

alt text

Add the target-group

alt text

Load-balancer is created successfully.

alt text

# `Creation of Auto-Scaling:`
Select the launch template.

alt text

Select the availability-zones.

alt text

Attach the load-balancer

alt text

alt text

Enter the desired capacity for instances.

alt text

Enter the minimum and maximum capacity for the instances

here i choose min=1,max=5

Select the scaling target policy as cpu-utilization

alt text

Then select the cpu limit as 50% for scaling the instance.

alt text

Add the notification : E-mail

You can get notification for every launching and termination of instances

alt text

The auto-scaling-group is created successfully.

alt text

The instance is initialized by the elastic-autoscaling-group

alt text

I connected to the instance and installed the stress in it.

The stress is a artificial load increser which increases the cpu-utilization than we can see the auto-scaling process in live.

we can have to enter the command : stress -c "percentage of cpu-utilization you want to increase" .

command : stress -c 400

alt text

The cpu-utilization increased

alt text

I got notification for launching of new instance

alt text alt text

I have successfully implemented the autocaling project

alt text

# `Conclusion:`
By harnessing the power of AWS autoscaling and load balancing, I've successfully enhanced the availability, scalability, and reliability of our application. In real-time This ensures a seamless user experience even during periods of high demand, ultimately driving customer satisfaction and business success.

# `The project is completed.`
