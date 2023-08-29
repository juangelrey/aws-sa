# EC2

## Types

- R: applications that needs a lot of RAM - in memory caches
- C: applications that needs good CPU: compute /databases
- M: applications that are balanced ("medium"): general /web app
- I: applications that need good local I/O
- G: applications that need a GPU: video rendering / machine learning

- T2/T3: burstable instances
- T2/T3 unlimited: unlimited burst

## Placement Groups

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/placement-groups.html

- Group strategies:
  - Cluster: low latency group in a single AZ. Useful for Big data job.
    - pros: great network (10Gbps bandwith between instances)
    - cons: if the rack fails, all insntances fails at the same time. Same AZ.
  - Spread: max 7 instances per group per AZ (critical apps), Used for maximize hight availability
    - pros: different hardware (up to 7 EC2 per AZ). Can span in multiple AZ. Reduce risk is simulataneos failure
    - cons: only 7 instances per AZ
  - Partigion: spread instances across many different partitions within an AZ. Scales to 100s of EC2 instances per group
    - pros: reduce the likelihood of correlated hardware failures for your applicatio
    - cons: only 7 partitions per AZ. up to 100s EC2 instances. Instances do not share rack

You can move an instance in or out ( you need to stop it first)

### Create

`aws ec2 create-placement-group --group-name my-cluster --strategy cluster --tag-specifications 'ResourceType=placement-group,Tags={Key=purpose,Value=production}'`

### Describe Tag

`aws ec2 describe-tags --filters Name=resource-type,Values=placement-group`

```
{
    "Tags": [
        {
            "Key": "Environment",
            "ResourceId": "pg-0123456789EXAMPLE",
            "ResourceType": "placement-group",
            "Value": "Production"
        },
        {
            "Key": "Environment",
            "ResourceId": "pg-9876543210EXAMPLE",
            "ResourceType": "placement-group",
            "Value": "Production"
        }
    ]
}
```

### Run instance

```
aws ec2 run-instances --placement "GroupName = my-cluster"
```

## Launch types

- On demand: short workload
- spot instances: short workloads, cheap, you can lose them
- reserved: minimum 1y. long workloads
  - all upfront payment, partial upfront payment, no upfront
- dedicated instances: no other customers share hardware
- dedicated hosts: entire physical server
  - software licenses operate at core

## Graviton

Best prices. Not availble for Windows

Graviton 2: 40%
Graviton 3: 3x perf compared to 2

## Metrics

- cpu: cpu utilization + credit usage
- network: network in and out
- status check: instance status, system statys
- disk: read/write
- RAM NOT INCLUDED

## Instance recovery

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-recover.html

Same private, public, elastic IP, metadata, placement group

- CW alarm: When the `StatusCheckFailed_System` alarm the recovery action is initiated
