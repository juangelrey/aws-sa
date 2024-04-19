# Direct connect


Supports the Link Aggregation Control Protocol (LACP) facilitating multiple dedicated physical connections to be grouped into link aggregation groups (LAGs)

- All connections must be dedicated connections and have a port speed of 1 Gbps, 10 Gbps, or 100 Gbps.
- All connections in the LAG must use the same bandwidth.
- You can have a maximum of two 100-Gbps connections in a LAG, or four connections with a port speed less than 100 Gbps. Each connection in the LAG counts toward your overall connection limit for the Region
- All connections in the LAG must terminate at the same Direct Connect endpoint.
- When you create a LAG, download the Letter of Authorization and Connecting Facility Assignment (LOA-CFA)

## Network requirements
Need one of:
- your network is co-located with an existing Direct connect location
- you are working with a Direct Connect Partner
- You are working with an independent service provider to connect to Direct Connect

### Co-locating
- deploy a router and supporting network equipment to a location with a physical uplink to AWS.
- Your router at the Direct Connect location is connected to the AWS router using a cross connect

### Contracting with a partner
- The Direct Connect Partner provides you with the physical equipment necessary to connect to an AWS router at the Partner's physical location.
- You use this physical link to configure the Direct Connect service to link your physical location with AWS

### Additional requirements
Meet the following conditions:
- use single-mode fiber with one of the following:
    - 1000BASE-LX (1,310 nm) transceiver for 1-gigabit Ethernet
    - 10GBASE-LR (1,310 nm) transceiver for 10-gigabit Ethernet
    - 100GBASE-LR4 for 100-gigabit Ethernet
- Auto-negotiation for the port must be deactivated.
- 802.1Q VLAN encapsulation must be supported
- Your device must support Border Gateway Protocol (BGP) and BGP MD5 authentication. 


### LOA-CFA
1. AWS will provide you with an LOA-CFA
2. LOA-CFA lets you show the operator of the facility hosting the AWS router that AWS approves your request to connect to the AWS router. 
3. complete the setup using the AWS Management Console

### Virtual interface types
- private virtual: permits traffic to be routed to any VPC in the same private IP space
- public virtual: permits traffic to be routed to any VPC or AWS regional resource with a public IP in the same region
- transit virtual: permits traffic to be routed to any VPC or AWS regional resource routable through Transit Gateway in the same region

## Pricing
Pay only what you use.
- port hours (determined by connection type)
- outbound data transfer (per Gb)