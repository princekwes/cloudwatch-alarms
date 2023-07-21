What is AWS CloudWatch?

AWS CloudWatch is a powerful monitoring and observability service provided by Amazon Web Services. It enables you to gain insights into the performance, health, and operational aspects of your AWS resources and applications. CloudWatch collects and tracks metrics, collects and monitors log files, and sets alarms to alert you on certain conditions.

Advantages of AWS CloudWatch:

  Comprehensive Monitoring: CloudWatch allows you to monitor various AWS resources such as EC2 instances, RDS databases, Lambda functions, and more. You get a unified v        of your entire AWS infrastructure.
  Real-Time Metrics: It provides real-time monitoring of metrics, allowing you to respond quickly to any issues or anomalies that might arise.
  Automated Actions: With CloudWatch Alarms, you can set up automated actions like triggering an Auto Scaling group to scale in or out based on certain conditions.
  Log Insights: CloudWatch Insights lets you analyze and search log data from various AWS services, making it easier to troubleshoot problems and identify trends.
  Dashboards and Visualization: Create custom dashboards to visualize your application and infrastructure metrics in one place, making it easier to understand the overall 
  health of your system.

  Services Used:
  1. Ec2
  2. CloudWatch
  3. SNS



1. Create An EC2 Instance - Ubuntu is fine with t2.micro
   
<img width="1299" alt="Screenshot 2023-07-21 at 6 41 52 AM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/3478348e-5084-4e51-8cec-e65c25a1f0c5">
Remember to do the following:
i. Create a keypair to help ssh into the instance
ii. For just demo purposes, Allow all traffic in your security group section

2. Use your keypairs generated to ssh into the Ec3 Instance
<img width="868" alt="Screenshot 2023-07-21 at 6 44 38 AM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/e50bc9d0-5d31-445a-afae-3ee875b529fb">

