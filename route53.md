# Route53

- DNS service
- ELBs do not have pre-defined IPv4 - use DNS name
- Alias - A
- CNAME - Canonical name
- Prefer Alias records

## DNS Types
- SOA
- NS
- CNAME
- MX
- PTR

## Routing polcies
- Simple
    - 1 record, multiple IPs
- Weighted
    - Proportion of traffic
- Latency-based
    - Measured time to server
- Failover
    - Healthcheck
    - Active/Passive configuration
- Geolocation
    - What it says on the tin - IP based geolocation
- Geoproximity
    - Not in CSAA
    - Route based on location of users + resources
- Multivalue answer routing
    - Simple, except with healthchecks

## Healthchecks
- Failing records removed until passing