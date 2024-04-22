# Monitoring & troubleshooting


## top metrics to track health of network
- bandwith capacity: maximum data transmission rate 
- throughput: network’s actual data transmission rate
- latency: delay between a node reqeusting data and when that data is finished being delivered
- packet loss: how many packets are dropped during data transmissions
- retransmission: when packets are lost, we need to retransmit them to complete a data request (indicator of congestion on the network)
- availability: or uptime, measures if the network is currently operational
- connectivity: connectoins between nodes are working.
- response time: measures the time it takes for a server to respond to a data request
- CW metrics:
    - Disk I/O
    - Network
    - CPU
    - NetworkIn/NetworkOut
    - NetworkPacketsIn/NetworkPacketsOut

## four kinds of controls
- directive: establish the governance, risk, and compliance models within which the environment operates. 
- detective: intended to identify and characterize an incident in progress and provide assistance during investigations and audits after the event has occurred
- preventive: designed to prevent an incident from occurring.
- responsive: intended to limit the extent of any damage caused by the incident


Directive and preventative security controls help establish a baseline


## how to implement network security
- firewall
- packet sniffer
- penetration testing

## attacks

- active:
    - masquerade attacks
    - message replay
    - message modification
    - DoS
- passive: an attacker analyzes traffic and the content of packets
    - man in the middle


## tools
- CW
- VPC flog logs
- Traffic mirroring: copy network traffic from an elastic network interface of an Amazon EC2 instance.
- VPC Reachability Analyzer: diagnostics tool that troubleshoots reachability between two endpoints in an Amazon VPC
- AWS Transit Gateway Network Manager: centrally manage your networks that are built around transit gateways
- AWS CloudTrail: Management Events & Data Events