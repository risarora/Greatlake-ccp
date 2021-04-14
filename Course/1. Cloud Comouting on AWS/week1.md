
## Week 1 - Learning Material - Compute, Organization & IAM (~ 3.5 Hours)

### Module 1 - Core Building Blocks, Abstraction, AWS Console (~20mins)
### Module 2 - Compute - Elastic Compute Cloud or EC2 (~1hr)
### Module 2a - AWS EC2 Step 3 - Advanced Features Part I (~25mins
### Module 2b - AWS EC2 Step 3 - Advanced Features Part II (~10
### Module 3 - How to SSH in to an EC2 Instance (~15mins)
### Module 4 - Load Balancing, Fault Tolerance & CloudWatch(~1hr)
#### Load Balancer Additional Information
<details>

##### Load Balancer (Additional Information)

A. Network Load Balancer

A Network Load Balancer functions at the fourth layer of the Open Systems Interconnection (OSI) model. It can handle millions of requests per second. After the load balancer receives a connection request, it selects a target from the target group for the default rule. It attempts to open a TCP connection to the selected target on the port specified in the listener configuration.

When you enable an Availability Zone for the load balancer, Elastic Load Balancing creates a load balancer node in the Availability Zone. By default, each load balancer node distributes traffic across the registered targets in its Availability Zone only. If you enable cross-zone load balancing, each load balancer node distributes traffic across the registered targets in all enabled Availability Zones.

If you enable multiple Availability Zones for your load balancer and ensure that each target group has at least one target in each enabled Availability Zone, this increases the fault tolerance of your applications. For example, if one or more target groups does not have a healthy target in an Availability Zone, we remove the IP address for the corresponding subnet from DNS, but the load balancer nodes in the other Availability Zones are still available to route traffic. If a client doesn't honor the time-to-live (TTL) and sends requests to the IP address after it is removed from DNS, the requests fail.

For TCP traffic, the load balancer selects a target using a flow hash algorithm based on the protocol, source IP address, source port, destination IP address, destination port, and TCP sequence number. The TCP connections from a client have different source ports and sequence numbers, and can be routed to different targets. Each individual TCP connection is routed to a single target for the life of the connection.

NLB is a great option for use cases where the client needs to keep the TCP connection open for long periods of time. If we use this for web applications using http(s) then we will observe that all the requests for a given user (browser instance) will always connect to a single backend web/application server.

Read more about AWS NLB here.
https://docs.aws.amazon.com/elasticloadbalancing/latest/network/introduction.html
 

B. Application Load Balancer

Recently, some additional features of the load balancer have been introduced. The summary of the ALB capabilities are as follows:

1. Weighted Target Groups for ALB - You can now use traffic weights for your ALB target groups; this will be very helpful for blue/green deployments, canary deployments, and hybrid migration/burst scenarios. You can register multiple target groups with any of the forward actions in your ALB routing rules, and associate a weight (0-999) with each one. For example, we can send 70% of the traffic to tg1 and the remaining 30% to tg2.

2. Least Outstanding Requests for ALB - You can now balance requests across targets based on the target with the lowest number of outstanding requests.

You can read the very short blog here.
https://aws.amazon.com/blogs/aws/aws-load-balancer-update-lots-of-new-features-for-you/

</details>

### Module 5 - Windows EC2 Instance, Instance Pricing (~ 15mins)
### Module 6 - Identity & Access Management (~15mins)


