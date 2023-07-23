# Exam scenarios for CloudFormation

**Q** - Need to review updates to a CloudFormation stack before deploying them in production

**A** - Use Change Sets

---

**Q** - Stack deployed and manual changes were made. Need to capture the changes and update the templates

**A** - Use drift detection and use Output to update template and re deploy the stack

---

**Q** - Need to update new version of App on EC2 and ALB. Must avoid DNS Changes and be able to rollback

**A** - Update the template with `autoscalingreplacingupdate` policy and perform and update

---

**Q** - Need to write a single template that can be deployed across several environments and regions

**A** - Use parameters to enter custom values and use `!Ref` intrinsic function to reference the parameters

---

**Q** - Tried to launch instance in a different region from a working template and it failed

**A** - Probably due to the AMI is not available in the region

---

**Q** - Cloudformation stack created for first time and fails with a `ROLLBACK_COMPLETE` status

**A** - To continue administrator must relaunch the template to create a new stack

---

**Q** - Template for infrastructure in one region used to deploy in another region and fails

**A** - Template likely referenced an AMI that does not exist in the new region and / or services that are not available in the new region

---

**Q** - Cloudformation stack fail and returns `UPDATE_ROLLBACK_FAILED` status

**A** - Fix the error that caused the rollback to fail and then select `CONTINUE UPDATE ROLLBACK` in the console

---

**Q** - Need to deploy a single cloudformation template across multiple accounts

**A** - Use stack sets

---

**Q** - Cloudformation deploys stack with a separate VPC for each app. Fails to deploy

**A** - Likely due to the VPC limit has been reached in the account

---

**Q** - Would like to manually adress any issues with cloudformation stack creation

**A** - Set the `OnFailure` property to `DO_NOTHING` in the template

---

**Q** - Cloudformation fails with "The image id '[ami-xxxxxxxx]' does not exist"

**A** - Likely due to the AMI is not available in the region

---

**Q** - When creating stack a wait condition error is experienced: ""Received 0 signals out of the 1 expected from the EC2 instance""

**A** - CHeck instance has a route through NAT device and in the CFN logs confirm that the CFN_signal command was executed successfully
