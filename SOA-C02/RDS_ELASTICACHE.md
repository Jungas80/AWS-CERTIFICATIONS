# Exam scenarios for RDS and ElastiCache

**Q** - Automated failover of a multi az DB ocurred

**A** - This maybe due to storage failure on primary DB or the instance type could have been changed

---

**Q** - Need to encrypt an unencrypted RDS database

**A** - Create a snapshot of the unencrypted database and then restore it to a new encrypted database

---

**Q** - RDS DB query latency is high and CPU utilization is at 100%

**A** - Scale up the instance type

---

**Q** - Need to share RDS DB snapshot with another AWS account. Data must be encrypted

**A** - Use an AWS KMS key to encrypt the snapshot and update key policy to grant acccounts with access to the key. Then share the snapshot with the other account

---

**Q** - DB needs to be made Highly Available to protect against AZ failure and updates can not impact availability during business hours

**A** - Change to multi AZ and use maintenance windows

---

**Q**
