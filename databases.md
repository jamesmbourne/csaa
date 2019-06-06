# Databases

# RDS

- Runs on VMs
- Not serverless (except Aurora Serverless)

* Relational OLTP

  - MS SQL
  - MySQL
  - Postgres
  - MariaDB
  - Oracle
  - Aurora

* Backups

  - Automated backups
  - Snapshots

* Read replicas

  - Multi-AZ
  - Increse read throughput
  - Alternative: enable Elasticache
  - Require backups to be enabled
  - Multi-region
  - Aurora or MySQL
  - Can promote to master

* MultiAZ for DR

  - Force failover by rebooting instance

* Encryption using KMS
  - Data at rest
  - Backups
  - Snapshots
  - Read replicas

# DynamoDB

- Serverless
- SSDs
- Eventually consistent

# RedShift

- RedShift OLAP (Online Analytics)
- Limited availablility
- Backups enabled 1 day default
- Can extend to 35 days
- Maintain 3 copies - original, replica (on compute nodes), S3
- Async cross-region replication to S3 for DR

## Elasticache

- Increase performance

- Memcached (simple)
- Redis (advanced)
    - Backups
    - Multi-AZ

## Aurora
- 2 copies per AZ
- 3 AZ minimum
- 6 copies
