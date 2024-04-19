# Connectivity concepts

## VPC Endpoints
- not allow traffic between your VPC and the other services to leave the Amazon network.
- Instances in your VPC do not require a public IP address to connect to services 

### Gateway VPC endpoints
- A gateway VPC endpoint targets specific IP routes in a VPC route table in the form of a prefix list.
- used for s3 or Dynamodb

### Interface endpoints
- an interface endpoint is an elastic network intervafe with a privatr IP 

### Gateway Load balancer endpoint
- You specify a Gateway Load Balancer endpoint as a target for a route in a route table
- 


## PrivateLink
-  a private connection between your VPCs and supported AWS services

### Benefits 
- security: 
    - secure and scalable way to privately connect to AWS hosted services
    - does not traverse the internet.
    - uses private IP addresses and security groups within a VPC 
- simplification:
    -  helps avoid security policies that limit benefits of internet gateways and complex networking
    - facilitates connectivity to services across different accounts and VPCs,
- capabilities:
    - gives on-premises networks private access to AWS services through Direct Connect
    - If you use AWS PrivateLink with a Network Load Balancer to route traffic to your service or application, clients can connect to any service you host.

### Considerations
- does not support IPv6
- Traffic will be sourced from the Network Load Balancer inside the service provider VPC.
- You can activate Proxy Protocol v2 to gain insight into the network traffic.
    - Network Load Balancers use Proxy Protocol v2 to send additional connection information such as the source and destination.
- Endpoint services cannot be tagged.
- The private Domain Name System (DNS) of the endpoint does not resolve outside of the VPC.
- Availability Zone names in a customer account might not map to the same locations as Availability Zone names in another account. 

### DNS
- Regional: An endpoint-specific DNS hostname is automatically generated and includes all zonal DNS hostnames generated for the interface endpoint
    - The hostname includes a unique endpoint identifier, service identifier, Region, and vpce.amazonaws.com in its name. 
        - vpce-0fe5b17a0707d6abc-29p5708s.ec2.us-east-1.vpce.amazonaws.com
- Zone: You can generate a zonal-specific DNS hostname for each Availability Zone in which the endpoint is available.
    - vpce-0fe5b17a0707d6abc-29p5708s-us-east-1a.ec2.us-east-1.vpce.amazonaws.com (includes zone us-east-1a)
- Private: can use a private DNS hostname to alias the automatically created into a friendly hostname 
    - myservice.example.com

### Pricing
- charged hourly for provisioned in each AZ + per Gb processed 
- There is no additional charge for using gateway endpoints.

*You might be able to reduce costs by selecting gateway endpoints for traffic destined to DynamoDB or Amazon S3.*