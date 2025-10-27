HW - DELIVERABLES (5 pts)
Must be in github repo link - 

You must create your own Network architecture with at least 3 public Subnets and 6 private subnets. Upload your network range in a document. Network architecture must include subnet masks and the AWS region it was designed for. The network architecture should be able to be utilized for building a VPC within the console.

Region (North Virginia) – IP Address Network (10.234.0.0/16)

Subnets 

(Public 1A) – 10.234.1.0/24
(Public 1B) – 10.234.2.0/24
(Public 1C) – 10.234.3.0/24
(Public 1D) – 10.234.4.0/24
(Public 1E) – 10.234.5.0/24
(Public 1F) – 10.234.6.0/24

(Private 1A) – 10. 234.11.0/24
(Private 1B) – 10. 234.12.0/24
(Private 1C) – 10. 234.13.0/24
(Private 1D) – 10. 234.14.0/24
(Private 1E) – 10. 234.15.0/24
(Private 1F) – 10. 234.16.0/24


Screenshot of the completed quiz at the end of the Udemy SAA section

![Udemy Networking Quiz Completion](image.png)

Screenshot of your high score on the binary game

![ Binary game High Score](image-1.png)



HW - BE A MAN CHALLENGE 4.1 (10 pts)

Must be in github repo link -

Create a VPC in your preferred region (must have at least 3 availability zones {same Network used above}). Inside your VPC, build a single Windows bastion host within a public subnet,

![Public Bastion Host Successful Initiation](image-2.png)

 and one Linux web server per availability zone, all  in different private subnets. Each Linux web server should also display different text and pictures. 
 
 Africa 

![Private EC2 through Bastion AZ:1A](image-6.png)

 Brazil

 ![Private EC2 through Bastion AZ:1B](image-7.png)
 
 Japan
 
![Private EC2 through Bastion AZ:1C](image-8.png)

 Take screenshots of the running Windows bastion host, the three Linux servers (highlighting the three different AZs in each photo), 
 
 [These two deliverables are shown above.]
 
 and a screenshot of a successful SSH connection to each Linux server from within the bastion host.


African Subnet

![Bastion Host SSH to Private EC2 Subnet in AZ:1A](image-9.png)

Brazilian Subnet

![Bastion Host SSH to Private EC2 Subnet in AZ:1B](image-10.png)

Japanese Subnet

![Bastion Host SSH to Private EC2 Subnet in AZ:1C](image-11.png)