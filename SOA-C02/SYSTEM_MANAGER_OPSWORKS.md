# Exam scenarios for Systems Manager and Opsworks

**Q** - App running on EC2 needs login credentials for a DB that are stored as a secure string in SSM Parameter Store

**A** - Create an IAM Role for the instance and grant permissions to read the parameter

---

**Q** - Linux instance are patched with Systems Manager Patch Manager. Application slow downs whilst updates are applied

**A** - Change the maintenance window to patch 10% of instances in the patch group at a time

---

**Q** - Custom linux AMI used with AWS Systems Manager. Can´t find the instance in session manager console

**A** - Need to add permissions to instance profile and install the SSM agent on the instances

---

**Q** - Multiple environments requiere authentication credentials for external service deployed using cloudformation

**A** - Store the credentials in SSM Parameter Store and pass an environment tag as a parameter in the template

---

**Q** - IAM Access Keys used to manage EC2 instances using the CLI. Company policies mandate that access keys are automatically disabled after 60 days

**A** - Use an AWS Congif rule to identify non-compliant access keys. Create a custom AWS Systems Manager automation document for remediation