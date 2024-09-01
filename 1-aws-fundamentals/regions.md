![alt text](images/RegionAZLocalZone.png)

# AWS Regions
- AWS Regions are clusters of data centers
- AWS Region is designed to be isolated from the other AWS Regions.
- When you view your resources, you see only the resources that are tied to the AWS Region that you specify. 
- Example of regions: us-east-1, eu-west-1, etc.
- Most services provided by AWS are regions scoped. This means a data for a service used in one region is not replicated in another region
## Region Selection
- **Governance and legal requirements**: Consider any legal requirements based on data governance, sovereignty, or privacy laws.

- **Latency**: Close proximity to customers means better performance. 

- **Service availability**: Not all AWS services are available in all Regions.

- **Cost**: Different Regions have different costs. Research the pricing for the services that you plan to use and compare costs to make the best decision for your workloads.

![alt text](images/RegionSelection.png)

# AWS Availability Zones (AZ)

- AWS Regions are divided into availability zones
- Each region has between 2 and 6 AZs. Usually they have 3
- Each AZ is one or more discrete data center with redundant power, networking an connectivity
- All AZs from a region are geographically separated from each other
- Even if they are separated, they have high bandwidth connection between them

# Local Zones
- You can use AWS Local Zones for highly demanding applications that require single digit millisecond latency to end users. 
  
  Examples include:
  - Media and entertainment content creation - Includes live production, video editing, and graphics intensive virtual workstations for artists in geographic proximity
  - Realtime multiplayer gaming - ncludes realime multiplayer game sessions, to maintain a reliable gameplay experience
  - Machine learning hosting and training or high performance, low latency inferencing
  - Augmented reality (AR) and virtual reality (VR) - Includes immersive entertainment, data driven insights, and engaging virtual training experience
- A Local Zone is an extension of an AWS Region that is geographically close to your users. 
- You can extend any VPC from the parent AWS Region into Local Zones. To do so, create a new subnet and assign it to the AWS Local Zone. 
- When you create a subnet in a Local Zone, your VPC is extended to that Local Zone. 
- The subnet in the Local Zone operates the same as other subnets in your VPC.
### Use case 
You should use AWS Local Zones to deploy AWS compute, storage, database, and other services closer to your end users for low latency requirements. With AWS Local Zones, you can use the same AWS infrastructure, services, APIs, and tool sets that you are familiar with in the cloud.
  
  e.g. Perth can be considered as a local zone for mining companies with high compute requirements.

# Edge Location
- An edge location is the nearest point to a requester of an AWS service. 
- Edge locations are in major cities around the world. They receive requests and cache copies of your content for faster delivery.
- To deliver content to end users with lower latency, you use a global network of edge locations that support AWS services. CloudFront delivers customer content through a worldwide network of point of presence (PoP) locations, which consists of edge locations and Regional edge cache servers.
- Regional edge caches, used by default with CloudFront, are used when you have content that is not accessed frequently enough to remain in an edge location. 
- Regional edge caches absorb this content and provide an alternative to the need to retrieve that content from the origin server. 
### Use case
One common use for edge locations is to serve content closer to your customers. A video file that is stored in Amazon Simple Storage Service (Amazon S3) in South America. The file is cached to an edge location near the customer to serve the video file faster to a customer in Asia. 
