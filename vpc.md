# VPC

- Logical gateways

## Components

- IGWs (or virtual private gateways)
- Route tables
- NACLs
- Subnets
- Security groups

## Subnets

- 1 subnet = 1 AZ

- AWS has 5 IP reservation in subnets

  - 0 network
  - 1 router
  - 2 DNS
  - 3 future use
  - 255 broadcast

- Auto-assign public IP = Public Subnet

## NACLs and SGs

- NACLs are stateless
- SGs are stateful

- SGs cannot span VPCs

- No transitive peering, must be 1-to-1

## Building

Defaults:

- Route table
- NACL
- SG

NOT default:

- Subnets
- IGW

1. VPC
2. Subnets
3. IGW
   - Attach
4. Route Table
    - Local full CIDR block
    - Main route table private
    - Custom route table - public
    - 0.0.0.0/0 - target IGW
    - ::/0 - target IGW
    - Associate with public SN
5. NAT Gateway/Instance
    - Allow private SNs to access internet
    - Must be placed in public subnet
    - Src/dest check disabled to allow handling traffic for other instances
    - Route table: 0.0.0.0/0 - NAT Gateway

## IGW

- Limit of 1 per VPC

## NAT Instance

- Disable source/dest check
- MUST be in a public subnet
- Private SN must have route to NAT instance
- Traffic limited by instance size
- Behind an SG

## NAT Gateway

- Managed service
- Autoscaling
- NOT behind an SG
- Redundancy within AZ
- 5Gps scaling to 45Gbps
- Update route table
- No source/dest check changes
- Multiple NAT gatways per AZ, configure routing to use local NGW

## NACLs

- Comes with default setup allowing ALL in + outbound traffic
- Custom ACL - deny all
- Each SN must have an associated NACL, falling back to default
- Able to block IPs on specific ports - impossible with SGs
- Priority list of rules, evaluated with lowest number first
- Allow trumps deny - deny should be before allow

## ELBs

- 2 public subnets required for internet-facing ELB

## Flow logs

- Cannot see flow logs to external VPCs
- Cannot tag
- Cannot modify after creation
- Not all traffic is monitored (AWS DNS, Windows licensing, instance metadata, DHCP, traffic to reserved IPs)

## Bastions

- Instance in private SN
- Placed in public subnet

## Direct Connect

- Conncet datacenter
- High throughput
- Secure

## VPC Endpoint

- Allows access to AWS services without public IPs
- Interface
- Gateway
  - S3
  - DynamoDB
