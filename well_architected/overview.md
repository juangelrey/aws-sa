# The Five pillars
https://wa.aws.amazon.com/wellarchitected/2020-07-02T19-33-23/wat.pillars.wa-pillars.en.html

- Operational Excellence
- Security
- Reliability
- Performance Efficiency
- Cost Optimization 


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


## Reliability 

### Best practices