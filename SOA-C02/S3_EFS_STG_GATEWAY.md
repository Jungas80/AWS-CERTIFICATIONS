# Exam scenarios for S3, EFS, AWS Storage Gateway

**Q** - User deleted some data in an EBS volume and there´s a recent snapshot. How can the data be recovered?

**A** - Create a new EBS volume from the snapshot and attach it to an instance to copy the deleted file across

---

**Q** - EBS volume runs out of space and need to prevent it to happen again

**A** - Use Cloudwatch agent on EC2 and monitor disk metrics with a Cloudwatch alarm

---

**Q** - Most cost effective storage option for big data apps that stores sequentially and infrequently accessed data

**A** - COLD HDD (SC1)

---

**Q** - EBS volume capacity is increased but can not see the new space

**A** - Extend the volume file system from the OS

---

**Q** - Need to replace user-shared drives. Must support POSIX permissions snd NFS protocols and be accesible from on-premise servers and EC2 instances

**A** - Use EFS

---

**Q** - Low latency access requiered for image files in an office location with synchronyzed backups to offsite location. Local access requiered and disaster recovery

**A** - Use an AWS Storage Gateway volume gateway configured as a stored volume

---

**Q** - Performance issues with ISCSI drives in volume gateway `cachehitpercent` metric is below 55% and `cachepercentused` is above 95%

**A** - Create a larger disk for cached volume and select it in the management console

---

**Q** - Tape archivel system needs replacement

**A** - Use AWS Storage Gateway tape gateway

---

