# Exam scenarios for Amazon VPC

**Q** - Need to identify the instances that are generating the most traffic using a NAT Gateway

**A** - Use VPC Flow Logs on the NAT Gateway ENI and use cloudwatch insights to filter based on source ip address

---

**Q** - Latency on a NAT Instance has increased, need a solution that scales on demand cost effectively

**A** - Use a NAT Gateway, NAT Gateways are managed by AWS and scale automatically

---

**Q** - NAT Gateway is not highly available across azs, only within an az

**A** - Use multiple NAT Gateways in different AZs

---

**Q** - NAT Instance deployed but not working

**A** - Make sure to disable source/destination checks

---

**Q** - Need to enable access to S3 without the instances using public IPs

**A** - Use a Nat Gateway or VPC Endpoint

---

**Q** - EC2 instance in private subnet can not reach the internet. Route Table has a route to a NAT Gateway with a status of blackhole

**A** - Indicates that the NAT Gateway has been deleted.

---

**Q** - Need to connect to S3 from EC2 using private network only. Must also ensure that only the instances can access the bucket

**A** - Create a VPC Endopoint and a bucket policy with a condition that limits S3 actions to the VPC Endpoint as the source

---

**Q** - VPC Endpoint setup to allow private IP address connectivity to S3 bucket, permissions configured, but instances still can´t access the bucket

**A** - Make sure the subnet has a target in the route table for the VPC Endpoint

---

**Q** - Need to manage EC2 Instances in a private subnet from an office using SSH but instances can not have internet access

**A** - Add a VGW and configure routing in the VPC and stablish a VPN connection to the office

---

**Q** - Need encryption in-transit and at rest for hybrid environment

**A** - Use an AWS VPN connection and use KMS keys to encrypt the data

---

**Q** - Network change was made that resulted in application to DB connection issues

**A** - Analyze the VPC Flow Logs to identify the issue

---

**Q** - Inbound and outbound internet connectivity is required EC2 instances

**A** - Need an entry in the route table for subnet that points to internet gateway and to attach an IGW to the VPC

---

**Q** - VPC peering connection setup between two different vpcs. Instances in private subnets still can´t reach each other

**A** - Make sure the route tables are updated to include the peering connection

---

**Q** - A company has configured a VPC peering connection between two  VPCs and needs to setup connectivity between instances in private subnets

**A** - Configure the VPC route tables with routes pointing to the adress range of the other VPC

---

**Q** - Company backing up one VPC to another in different region. All data must be private and encrypted

**A** - Use inter-region VPC peering which encrypts across the AWS global network

---

**Q** - Malicious IP identified and must be blocked from all ingress and egress connectivity

**A** - Add a rule to a network ACL for all affected subnets

---

**Q** - VPC connected to a datacenter by VPN user pings private subnet instance from on-prem computer and fails. VPC flow logs shows accept for inbound but reject for outbound traffic

**A** - Modify the network ACL to allow outbound traffic
