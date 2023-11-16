- Network drive that can be attached to a EC2 instance
- Think of it as a "network pendrive"

**Important points**
- It is a network drive, so there is latency between EC2 and volume. Also it can be unmounted from one instance and attached to another instance.
- It is locked to an availability zone, but we can create snapshots and transfer those across AZs
- We have to provision capacity like memory or IOPS (I/O operations per second)

**EBS Snapshots**
- Templates from which EBS volumes can be created
- There is archive tier in which the recovery time is 24-48 hours (75% cheaper)
- There is recycle bin for snapshots as well