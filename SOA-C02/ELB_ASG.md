# Exam scenarios for ELB and EC2 Auto-Scaling

**Q** - Design requiered for highly available and secure website on EC2 with ALB, and DB on EC2

**A** - Launch ALB in public subnets, web serviers in private subnets and db layer in private subnets - All layers in different AZs

---

**Q** - A company metrics for and ALB have dropped from 6 to 2. Determine the cause

**A** - The health checks on target EC2 are failing.

---

**Q** - An instance attached to an ALB exceeded the unhealthy threshold for consecutive health check failures. Whay will happen?

**A** - Health checks will continue and the ALB will take the instance out of service

---

**Q** - Requirement to track the source IP of clients and the instance that process the request

**A** - Check the ALB Access Logs for this information

---

**Q** - Requirement to trigger an alarm when all instances are unhealthy

**A** - Use cloudwatch with the condition `AWS/ApplicationELB/UnHealthyHostCount` <= 0

---

**Q** - Need to check why users cannot connect to web server public IP and port (behind ALB)

**A** - Check the VPC Flow Logs

---

**Q** - Http code_ELB_5xx_count Amazon Cloudwatch metrics are noticed for an ALB. Determine the cause

**A** - The target group may not contain any healthy instances

---

**Q** - Cloudwatch shows 4xx error for App with ELB but the instances have already been terminated and need to analyse the root cause

**A** - Use ELB Access Logs to retrieve info from S3 bucket to find the originator of the requests

---

**Q** - Need a Load Balancer where specific static public IP addresses can be whitelisted by clients

**A** - Use a Network Load Balancer

---

**Q** - Poor performance has been experienced for an Application running on EC2

**A** - Use EC2 auto-scaling to dynamically scale

---

**Q** - 503 and 504 errors exerienced and instances have high cpu utilization

**A** - Use EC2 auto-scaling to dynamically scale

---

**Q** - ASG does not launch instances during busy periods despite max capacity not being reached

**A** - Could be due to service limits (check trusted advisor) or check for running instances requests in cloud trail in case they are failing

---

**Q** - Need to analyze instances before they are terminated

**A** - Use EC2 Auto Scaling Lifecycle Hooks to pause the termination process

---

**Q** - Auto-scaling scales based on queue depth but at begginning of day the app is slowing down

**A** - Create a scheduled scaling policy

---

**Q** - Create gighly available EC2 autoscaling group single instance app

**A** - Use at least 3 AZs, min size of 2, desired capacity of 2 and max size of 2

---

**Q** - Elastic Beanstalk worker node reads messages from SQS queue. Auto scaling scales instances. App slows down when number of messages in queue increases

**A** - Update ASG to scale based on SQS queue depth

---

**Q** - ALB is expecting a large spike in traffic. And the application is memory intensive

**A** - Use the `requestcountpertarget` metric to control scaling

---

**Q** - New instances in an ASG are not showing up in the aggregated metrics. Step scaling is used

**A** - Likely due to the warmup period has not yet expired
