# The Five pillars
https://wa.aws.amazon.com/wellarchitected/2020-07-02T19-33-23/wat.pillars.wa-pillars.en.html


<details>
<summary>Operational excellence</summary>

## Operational excellence
- Perform operations as code
- Make frequent small reversible changes
- Refine operations procedures frequently
- Anticipate failure
- Learn from all operational failures


### Best practices
- Organization:
    - Evaluate external customer needs
    - Evaluate internal customer needs
    - Evaluate governance requirements
    - Evaluate compliance requirements
    - Evaluate threat landscape
    - Evaluate trade offs
    - Manage benefits and risks
- Prepare
    - design telemetry
    - design for operations (version control, test and validate changes)
    - mitigate deploymenbt risks
- Operate
    - understand workload health
    - understand operational health
    - respond to events
- Evolve
    - learn share & improve

</details>
<details>
<summary>Security</summary>

## Security
- implement a strong identity foundation
- turn on traceability
- apply security at all layers
- automate security best practices
- protect data in transit and at rest
- keep people away from data
- prepare for security events

### Best practices
- security foundations
    - shared responsability
    - operating workloads securely
- identity and access management
    - strong sign in mechanisms
    - temp creds
    - store and use secrets securely    
    - audit and rotate creds periodically
    - set up user groups and attributes
    - permissions management
        - define access reqruiements
        - grant least privilege access
        - establish emergency access process
        - reduce permissions continuously
        - define guardrails for your org
        - manage access based on lifecycle
        - analyze public and cross account acesss
        - share resources securely in your organization
        - share resources securely with a third party
- detection
    - configure services and application logging
    - analyze logs and metrics
    - automate response to events
    - implement actionable security events
- infrastructure protection
    - create network layers
    - control traffic at all layers
    - automate network protection
    - implement inspection and protection
    - protecting compute
        - perform vulnerability management
        - reduce attack service
        - implement managed services
        - automate compute protection
        - help peopl perform aactions at a distance
        - validate software integrity
- data protection
    - classifying data
        - identify data in your workload
        - define data protection controls
        - automate identification and classification
        - define data lifecycle management
    - protecting data at rest
        - implement secure key management
        - enforce encryption at rest
        - auomate data at rest protection
        - enforce access control
        - use mechanisms to keep people away from data
    - protecting data in transit
        - implement secure key and ceritifcate management
        - enforce encryption in transit
        - automate detection of unintended data access (like guard duty)
        - authenticate netowrk communications
- incident response
    - design goals of cloud response
        - establish response objectives
        - document plans
        - respond using the cloud
        - know what you have and what you need
        - use redeployment mechanisms
        - automate where possible
        - choose scalable solutions
        - learn and improve your process
    - educate
    - prepare simulate & iterate
- application security
    - train for app security
    - automate testing throughhout development and release lifecycle
    - perform regular penetration testing
    - perform manual code reviews
    - centralize services for packages and dependencies
    - deploy software programatically
    - regularly assess security properties of pipelines
    - build a program that embeds security ownership in workload teams

</details>

<details>
<summary>Reliability</summary>

## Reliability

- automatically recover from failure
- test recovery procedures
- scale horizontally to increase aggregage workload availability
- stop guessing capacity
- manage change in automation



### Best practices
- foundations
    - manage service quotas and constraints
        - stay aware of service quotas and constraints
        - manage service quotas across accounts and regions
        - accommodate fixed service quotas and constraints through architecture
        - monitor and manage quotas
        - automate quota management
        - ensure a sufficient gap exists between current quotas and maximum usage
    - plan network topology
        - use highly available network connectivity for workload public endpoint
        - provision redundant connectivity between cloud and on premises environments
        - ensure IP subnet allocation accounts for expansion and availability
        - prefer hub and spoke topologies over many to many mesh
        - enforce non overlapping private IP ranges in connected address spaces
- workfload architecture
    - design workload service architecture
        - how to segment workload
        - build services focused on specific business domains and functionality
        - provide service contracts per API
    - design interactions in a distributed system to prevent failures
        - idenfity which kind of distributed system is required
        - implement loosely coupled dependencies
        - do constant work
        - make all responses idempotent
    - design interactions in a distributed systems to mitigate
        - implement graceful degradation to transform hard dependencies to soft
        - throttle requrests
        - control and limit retry calls
        - fail fast and limit queues
        - set client timeouts
        - make services stateless where possible
        - implement emergency levers
- change management
    - monitor workload resources
        - monitor all componenents for the workload
        - define and calculate metrics
        - send notifications
        - automate responses
        - perform analytics 
        - conduct reviews regularly
        - monitor end to end tracing of requests through your system    
    - design a workload to adapt to changes in demand
        - use automation when obtaining or scaling resources
        - obtain resources upon detection of impairment to a workload
        - obtain resources that more resources are needed for a workload
        - load test your workload
    - implement change
        - use runbooks for standard activities such as deployment    
        - integrate functional testing as part of your deployment
        - integrate resiliency testing as part of the deployment
        - deploy using inmmutable infrastructure
        - deploy changes with automation
- failure management
    - back up data
        - idenfity and back up all data that needs to be backed up
        - secure and encrypt backups
        - perform data backup automatically
        - perform periodic recovery of data to verfy backup integrity and procesess
    - use fault isolation to protect workload
        - deploy workload to multiple locations
        - select appropiate locations for your multi location deployment
        - automate recovery for components constrained to a single location
        - use bulkhead architectgures to limit scope of impact
    - design workload to withstand component failures
        - monitor all components of workload to detect failures
        - fail over to healthy resources
        - automate healing on all layers
        - rely on data plane, not control plane, during recovery
        - use static stability to prevent bimodal behavior
        - send notifications when event impact availability
        - arhictect product to meet availability targets and uptime SLAs
    - test reliability
        - use playbooks to investigate failures
        - perform post incident analysis
        - test functional requirements
        - test scaling and performance requirements
        - test resiliency using chaos engineering
        - conduct game days regularly
    - plan for disaster recovery
        - define recovery objectives for downtime and data loss
        - use defined reovery strategies to meet recovery objectives
        - test disaster recovery implementation to validate implementation
        - manage configuration drift at the DR site or region
        - automate recovery
</details>

<details>
<summary>
Performance Eficiency
</summary>

## Performance Eficiency
- democratize advanced techonlogies
- go global in minutes
- use serverless architectures
- experiment more often
- consider mechanical sympathy

### Best practices
- selection
    - performance architecture selection
        - understand the available services and resources
        - define a process for architectural choices
        - factor cost requirements into decisions
        - use policies or reference architecture
        - use guidance from cloud provider or an appropiate partner
        - benchmark existing workloads
        - load test your workloads
    - compute architecture selection
        - understand available compute configuration options
        - evaluate available compute options
        - collect compute related metrics
        - determine required configuration by rightsizing
        - use available elasticity of resources
        - continually evaluate compute needs based on metrics
    - storage architecture selection
        - understand storage characteristics and requirements
        - make decisions based on access patterns and metrics
        - evaluate available configuration option
    - database architecture selection
        - understand data characteristics
        - evaluate the available option
        - collect and record database performance metrics
        - choose data storage based on access patterns 
        - optimize data storage based on access patterns and metrics
    - network architecture selection
        - understand how networking impacts performance
        - evaluate available networking features
        - choose appropiately sized dedicated connectivity or vpn for hybrid workloads
        - leverage load balancing and encryption offloading
        - choose network protocols to improve performance
        - chooose your workloads location based on network requirements
        - optimize network configuration based on metrics
- review
    - evolve workload to take advantage of new releases
        - stay up to date on new resources and services
        - define a process to improve workload performance
        - evolve workload performance over time
- monitoring 
    - monitoring resources to ensure expected performance
        - record performance relatec metrics
        - analyze metrics when events or incidents occur
        - establish kpis to measure workload performance
        - use monitoring to generare alarm based notifications
        - review metrics at regular intervals
        - monitor and alarm proactively
- trade offs
    - using tradeoffs to improve performance
        - understand areas where performance is most critical
        - learn about design patterns and services
        - identify how trade offs impact customers and efficiency
        - measure impact of performance improvements
        - use various performance related strategies
</details>

<details>
<summary>Cost optimization</summary>

## Cost optimization

- practice cloud financial management
- adopt a consumption model
- measure overall efficency
- stop spending money on undifferentiated heavy lifting
- analyze and attribute expenditure
### Best practices
- practice cloud financial management
    - establish a cost optimization function
    - establish a parternship between finance and tech
    - establish cloud budget and forecasts
    - implement cost awareness in your org processes
    - report and notify on cost optimization
    - monitor cost proactively
    - keep up to date with new service releases
    - create a cost aware culture
    - quantify business value from cost optimization
- expenditure and usage awareness
    - governance
        - develop policies based on your organization requirements
        - implement goals and targets
        - implement an account structure
        - implement groups and roles
        - implement cost controls
        - track project lifecycle
    - monitor cost and usage
        - configure detailed information sources
        - add organization information to cost and usage
        - idenfity cost attribution categories
        - establish organization metrics
        - configure billing and cost management tools
        - allocate costs based on workload metrics
    - decomission resources
        - track resources over their lifetime
        - implement a decomissiioning process
        - decomission resources
        - decomission resources automatically
        - enforce data retention policies
- cost effective resources
    - evaluate cost when selecting services
        - identify organization requirements for cost
        - analyze all workload components
        - perform through analysis of each component
        - select software with cost effective licensing
        - select components to optimize cost in line with organization priorities
        - perform cost analysis for different usage over time
    - select correct resource type, size and number
        - perform cost modeling
        - select resource type size and number based on data
        - select resource type, size and number automatically based on metrics
    - select pricing model
        - perform pricing model analysis
        - implement regions based on cost
        - select third party agreements with cost efficient terms
        - implement pricing models for all components of a workload
        - perform pricing model analysis at management account level
    - plan for data transfer
        - perform data transfer modeling
        - select components to optimize data transfer cost
        - select services to reduce data transfer cost
- management of demand and supply resources
    - perform analysis on workload demand
    - implement buffer or throttle to maanage demand
    - supply resources dynamically
- optimization over time
    - develop a worklaod review process
    - review and analyze this workload regularly
    - perform automations for operations
</details>

<details>
<summary>Sustainability</summary>

## Sustainability
- understand your impact
- establish sustainability goals
- maximize utilization
- antiticipate and adopt new more and efficient hardware and software offerings
- use managed services
- reduce the downstream impact of your cloud workloads
### Best practices
- region selection
- alignment to demand
    - scale infrastructure with user load
    - align SLAs with sustainability goals
    - stop the creation and maintenance of unused assets
    - optimize geographic of workloads for user locations
    - optimize team members resources for activities performed
    - implement buffering or throttling to flatten the damand curve
- software and architecture patterns
    - optimize software and architecture for async and scheduled jobs
    - remove or refactor workload components with low or now use
    - optimize areas of code that consume the most time or resources
    - optimize impact on customer devices and equipment
    - use software patterns and architectures that support data access and storage patterns
- data patterns
    - implment a data classfication policy
    - use technology that support data access and storage patterns    
    - use policies to manage the lifecycle of your datasets
    - use elasticity and automation to expand block storage or file system
    - remove unnedeed or redundant data 
    - use shared file systems or object storage to access common data
    - minimize data movement across networks
    - back up data only when difficult to recreate
- hardware and services
    - use the minimum amount of hardware
    - use instance types with the least impact
    - use managed services
    - optimize your use of hardware based compute accelerators
- process and culture
    - adopt methods that can rapidly introduce sustainability improvements
    - keep your workwload up to date
    - increase utilization of build environments
    - use managed device farms for testing
</details>