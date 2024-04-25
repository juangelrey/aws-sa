# Cloudwatch


## Useful queries

### top 15 paquets across hosts

```
stats sum(packets) as packetsTransferred by srcAddr, dstAddr    
| sort packetsTransferred  desc   
| limit 15
```

### top 15 byte transfers for hosts in a given subnet

```
filter isIpv4InSubnet(srcAddr, "192.X.X.X/24")    
| stats sum(bytes) as bytesTransferred by dstAddr    
| sort bytesTransferred desc    
| limit 15
```

### IP addresses that use specific protocols

```
filter protocol=6 | stats count(*) by srcAddr 
```
This is for TCP protocol.  Replace the 6 with 17 for UDP, and so on. 

### IP addresses that skipped flow log records during the caputure window

```
filter logStatus="SKIPDATA"   
| stats count(*) by bin(1h) as t    
| sort t
```


### 10 DNS resolvers with the highest number of requests

```
stats count(*) as numRequests by resolverIp    
| sort numRequests desc   
| limit 10
```

### 25 most recently added log events
```
fields @timestamp, @message | sort @timestamp desc | limit 25
```

### List og log events that are not exceptios

```
fields @message | filter @message not like /Exception/
```