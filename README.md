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


Create An EC2 Instance - Ubuntu is fine with t2.micro
   
<img width="1299" alt="Screenshot 2023-07-21 at 6 41 52 AM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/3478348e-5084-4e51-8cec-e65c25a1f0c5">
Remember to do the following:

i. Create a keypair to help ssh into the instance

ii. For just demo purposes, Allow all traffic in your security group section

Use your keypairs generated to ssh into the Ec3 Instance
<img width="868" alt="Screenshot 2023-07-21 at 6 44 38 AM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/e50bc9d0-5d31-445a-afae-3ee875b529fb">

Head back to the AWs Console; Select your Instance, scroll down and head to the monitoring tab. 

Click on "Manage Detailed Monitoring"
<img width="1433" alt="Screenshot 2023-07-20 at 9 19 26 PM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/efdbe2bd-2202-4eef-b624-b9197ebc8b48">

Enable detailed monitoring for this instance to help cloudwatch get more information
<img width="775" alt="Screenshot 2023-07-20 at 9 19 38 PM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/3baa081d-3a40-400b-b04c-1e053732155a">

Now Head to the search bar at the top and search for cloudwatch. 
- <i>little tip: get your instance id before heading to cloudWatch.</i>

Inside CloudWatch; Click on "All Alarms" and to the right side off the page, click on "Create alarm".
<img width="1680" alt="Screenshot 2023-07-21 at 7 00 51 AM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/1dc32a53-026c-49ba-bb3a-0d4642f88f02">

Click on "Set Metric"
<img width="1291" alt="Screenshot 2023-07-21 at 7 03 54 AM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/41d2a682-4f47-4a76-99fa-e77a3a903d51">

Click on "EC2"
<img width="1485" alt="Screenshot 2023-07-21 at 7 04 55 AM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/b18abcb5-3966-443a-b3ef-132aab34a558">

Click on "Per-Instance Metrics". Remember the insstance id i asked you to copy, paste it in the search bar.
<img width="1481" alt="Screenshot 2023-07-21 at 7 07 14 AM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/41c9d2f1-39bf-4419-83b9-a8ff9416f6c4">

After entering your instance id, scroll through the data showing below and check CPUUtilisation close to your instance id. And choose "Select metric"
<img width="1483" alt="Screenshot 2023-07-21 at 7 14 09 AM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/369cf94b-09b1-453f-a28a-2016fb5d1268">

Now click on "Statistic" and choose Maximum. and also click on "Period" and select your prefered time. I ssuggect 1 minute.
<img width="1139" alt="Screenshot 2023-07-21 at 7 16 15 AM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/4213895f-1723-4cc2-b8cb-286c658e3b8d">

Scroll down. Under Conditions and under "Whenever CPUUtilization is..." choose "Greater or Equal" and enter 50 in the "than…" column  and click on Next...
<img width="872" alt="Screenshot 2023-07-21 at 7 18 23 AM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/107e12ca-d374-4a4b-8b60-445120dd999f">

On the next page, keep the "Alarm state trigger" settings same and under "Send a notification to the following SNS topic" choose "Ceater New Topic". Give it a name or leave it to default. On the next tab, enter your preferred email addresss to receive notifications. and click "Create Topic".
<img width="1118" alt="Screenshot 2023-07-21 at 7 48 55 AM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/8e81912b-76ab-4653-a97c-6dd34886229c">

Leave all other setting sto default and click "Next"

Check your inbox or spam to confirm receipt of the email from sns and confirm the subscription.
<img width="1377" alt="Screenshot 2023-07-21 at 7 55 59 AM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/89e9f021-f02c-43e5-9dd8-7dce299041f0">

Click on "Confirm Subscription"
<img width="1365" alt="Screenshot 2023-07-21 at 7 56 23 AM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/a6ba05eb-e536-4e48-89ed-7b6e1ce35ccf">

Subscription Confirmed - head back to Cloudwatch to continue configuration
<img width="594" alt="Screenshot 2023-07-21 at 7 56 38 AM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/4b7cf72a-2646-4672-90f7-7dd15927afb7">

Give your alarm a name for indentification. Also enter a message that will come with the alert to let you know the particular alert or issue to give attention to.
Click "Next"
<img width="911" alt="Screenshot 2023-07-21 at 7 59 52 AM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/81c6d99c-520a-4747-9a09-a6112e5e62a2">

On the next page, scroll down and click "Create Alarm".
Setup is now done.

Now click the alarm you just created and see the updates displaying there:
<img width="1420" alt="Screenshot 2023-07-21 at 8 03 51 AM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/52d1f157-2f13-49d5-a20d-26fa007edb62">

<img width="1429" alt="Screenshot 2023-07-21 at 8 04 10 AM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/ed93c380-7ede-4c9d-a3f2-1f532590c251">

Now lets go to your terminal and create the file that will spike the CPU for us to get alerts.

In your terminal, with ssh into the ec2 instance done, use vim to create a file called "cpuspike.py" and you can give it any name but make sure the .py extension added.

Open the "cpu_spike.py" in the repo and copy the code into the file you just created::
Save and exit.

Run Python3 cpuspike.py and head to the cloudwatch to see the alarm show a red sign that its traggered.
<img width="1677" alt="Screenshot 2023-07-20 at 9 15 21 PM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/693b6ed5-caf8-4c79-b598-2b9a273a5184">

<img width="1420" alt="Screenshot 2023-07-20 at 9 15 12 PM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/c08d183b-4137-4518-ade3-cdbb1515d7b5">

<img width="1678" alt="Screenshot 2023-07-20 at 9 15 02 PM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/53e71f6e-297f-4937-9c2c-5f785c1fc919">

Head to your email inbox to see an email alert sent to you:

<img width="1338" alt="Screenshot 2023-07-20 at 9 12 59 PM" src="https://github.com/princekwes/cloudwatch-alarms/assets/1629130/3476deeb-5a1f-44c5-bbca-267c79de20db">

Congratulations, you just setup your first cloudwatch alert and linked it to sns to send you notifications. Take time and explore more ways to get the best out of cloudwatch.

Thank you

Special thanks to iam-veeramalla - https://www.youtube.com/@AbhishekVeeramalla




