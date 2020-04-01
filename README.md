# aws-container-well-architected-review

## Security

- How do you protect the sensitive data such as passwords in the containers? parameter store, secrets manager, kube secrets
- How are you defining the roles and responsibilities to the container system?
- How are you enforcing network and host-level boundary protection? private subnet, internet access
- How are you protect against vulnerabilities on the EC2 instances (worker nodes)?
- How are you protect against vulnerabilities on the container? Any scan on static or running images?
- Have you minimised your container footprint?
- What user do you run as in the container? root or non-root
- How are you classifying your data?
- How are you encrypting and protecting your data at rest?
- How are you encrypting and protecting your data in transit? From LB to task/pod. From task/pod to task/pod.
- How are you managing the keys and IAM roles on the EC2?
- Any IAM roles per task/pod?
- How are you encrypting and protecting your data in transit?
- How do you manage your incidence response?


## Reliability

- Are you aware of the ECS/EKS service limits?
- How do you design your network topology? EKS: private endpoint, network policies
- How does your service discover one another? DNS, cloud map, service mesh
- How do you design your CIDR?
- How do you define health checks of the containers?
- How does your system withstand component failures?
- How are you testing your resilience?

## Performance

- Have you performed load test?
- Have you set containers soft and hard limits?
- Have you applied tasks/pod scaling? EKS: HPA/VPA
- Have you applied hosts scaling? ECS: EC2 autoscaling. EKS: EC2 autoscaling, Cluster autoscaler
- Are your containers stateful or stateless? EKS. EBS/EFS/Fsx CSI autoscaler
- How do you backup the stateful data?
- How do you detect bottleneck/latency in a microservice? X-ray, Dynatrace

## Operations

- How do you promote the container image across various environments?
- What is the tagging strategy for your images? eg. unique build id 
- How do you automate infrastructure? eg. Terraform, Cloud Formation, CDK, EKSCTL
- How do you execute the CICD?
- How do you minimise application deployment downtime? Any bluegreen deployment?
- How do you patch/upgrade the container cluster? EKS: managed and unmanaged nodes
- Have you offload non-functional requirements to a sidecar?
- How are you capturing and analyzing application logs? cloudwatch logs, elastic search
- How are you capturing and analyzing metrics? prometheus, container-insights

## Cost Optimization

- Is tagging implemented?
- Have you considered data transfer charges?
- Any reserved instances/savings plan?
- Is the workload suitable for spot?
- Have you cosidered fargate?
