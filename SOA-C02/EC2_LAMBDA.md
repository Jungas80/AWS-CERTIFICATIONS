# Exam scenarios EC2 and Lambda

**Q** - Administrator needs to check if any EC2 instances will be affected by scheduled hardware maintenance

**A** - Check the AWS PERSONAL HEALTH DASHBOARD

---

**Q** - Scheduled hardware maintenance will affect a critical EC2 instances

**A** - Stop and start the instance to move it to different underlying hardware

---

**Q** - When lauching an EC2 instance the `insufficient instance capacity` error is experienced

**A** - This means AWS does not currenty have enough capacity to service the request for that instance type. Try a different Availability Zone or instance type


---

**Q** - The error `Instance limit exceeded` is experienced when launching an EC2 instance

**A** - EC2 instances are limited to 20 per region by default. This can be increased by a support ticket to AWS to increase the limit

---

**Q** - System status checks fail on an EC2 instance

**A** - This means the instance is having issues with the underlying hardware. Try stopping and starting the instance to move it to different underlying hardware

---

**Q** - For seecurity compliance reasons EC2 instances must not be able to access the internet

**A** - Launch them in a private subnet without a NAT gateway or NAT instance

---

**Q** - EC2 instances must communicate with an internet based service which whitelists a single source IP address

**A** - Place the instances behing a NAT gateway or NAT instance as the device will have a single public IP address which can be whitelisted

---

**Q** - A distributed application is running on EC2 and can handle proceessing interruptions. Determine the best pricing model to use

**A** - Use Spot instances as the application can handle interruptions

---

**Q** - Define AWS responsibility for EC2 hardware according to the AWS shared responsibility model

**A** - AWS is responsible for the underlying hardware.

---

**Q** - A nightly job runs on EC2 instances and stores results in S3. Takes 2 hours using multiple on demand isntances. If it fails it must start again. Determine the best pricing model to use

**A** - Request a spot block for the time required

---

**Q** - An asynchronous process runs on EC2 and feeds data to a data warehouse for weekly / monthly reporting. Determine the best pricing model to use

**A** - Use spot instances as the asynchronous process can handle interruptions. The reporting means the application can handle interruptions if AWS needs to reclaim the spot instance

---

**Q** - Need to track EC2 and on premise servers memory usage

**A** - Install the unified CloudWatch agent on both EC2 and on premise servers (or use a script)

---

**Q** - EC2 autoscaling automatically ternimates an instance due to a health check failure but the administrator needs to track the logs to determine the cause

**A** - install the unified CloudWatch agent on the instance to stream the logs to CloudWatch Logs

---

**Q** - There is a suspected memory leak on an EC2 instance

**A** - Install the unified CloudWatch agent to monitor memory usage

---

**Q** - Abd AWS Lambda function is expected to see a large increase in traffic and must scale to handle the increased load

**A** - Ensure the concurrency limit is set to a high value than the expected simultaneous requests

---

**Q** - Need to invoke a Lambda function every 5 minutes

**A** - Create an event rule to invoke the function every 5 minutes

---
