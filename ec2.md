# EC2

## Disk types

- gp2 (General purpose SSD) 16,000 IOPS
- io1 (Provisioned IOPS SSD) 64,000 IOPS
- st1 (Throughput optimised HDD)
- sc1 (Cold HDD)
- Standard (EBS Magnetic) - previous gen HDD

## Instance Metadata

- `curl http://169.254.169.265/latest/user-data`

## EFS

- Network file share
- Elastic capacity
- Mountable to multiple EC2 instances
- NFSv4
- Multi-AZ
- Read after write consistency
- Thousands of connections

## Placement Groups

- Clustered Placement Groups (single-AZ)
  - Low network latency
  - High network throughput
- Spread Placement Groups (multi-AZ)
  - Reduce risk of failures
- Can't move instances/merge PGs

## Security Groups

- Stateful
- Inbound implies outbound
- Cannot block specific IP
- Allow, not deny (deny all by default)

## Snapshots

- S3 backed
- Stop instance ideally
- Volume in same AZ
- Full and delta backups
- Automatically encrypted
- Shareable

## AMIs

- Can create from volume and snapshots
- Move instance: Snapshot instance -> Create AMI -> Launch in new AZ
- Move region: Snapshot instance -> Create AMI -> Copy AMI -> Launch in new region

## Instance store

- Local scratch disks
- Data loss on failure
- Rebootable

## CloudWatch

- 5 minutes by default
- 1 minute detailed monitoring available
- Alarms

## CloudTrail

- Audit API calls in AWS platform

## Instance Types

- F - FPGA
- I - IOPS
- G - GPU
- H - High disk throughput
- T - General purpose
- D - Density of storage
- R - RAM
- M - Main choice
- C - Compute
- P - Pics (graphics)
- X - Extreme - High memory
- Z - Extreme - High memory AND CPU
- A - ARM
- U - Bare metal
