# EC2

## Types

- Target tracking scaling
  - most simple and easy, for example: ASG cpu at 40%
- simple / Step scaling
  - when a CW alarm is triggered (cpu >80%), add 2 units
- scheduled actions
  - anticipate a scaling based on known usage patterns

## Predictive Scaling

- continously forecast load and schedule scaling ahead

Good metrics to scale on

- CPUUtilization: average cpu
- RequestCountPerTarget
- Average Network In / Out
- Any custom metric

### Other things

- Spot fleet support (mix on spot and on demmand instances)
- Lifecycle hooks
- To upgrade an AMI must update the launch configuration / template

## Instance refresh

- Goal: update launch template and then recreate all EC2 instences
- For this we can use the native feature of instance refresh
- Sertting of minimun healthy percentage
- Specify warm up time

## Scaling processes

- Launch: add a new ec2 to the group, increasing capacity
- Terminate: removes an ec2 instance from the group, decreasing its capacity
- HealthCheck: checks the health of the instances
- ReplaceUnhealthy: terminate unhealthy instances and recreate them
- AZRebalance: balancer the number of ec2 instances across AZ
- AlarmNotification: accept notification from CW
- ScheduledActions: perfrom actions created
- AddToLaodBalancer: Adds intances to the load balancer r TargetGroup
- InstanceRefresh: refreshes!

## Health checks

- EC2 status checks / ELB health checks (http)
- ASG will launch a new instance after terminating an unhealthy one
- Make sure the health check is simple and checks the correct thing

# Updating an application
