# Summary

Installs AWS App Mesh Ingress Gateway on an Amazon Elastic Kubernetes Service (EKS) cluster, letting  outside-the-mesh traffic to enter the mesh and allowing tracing and routing of requests at the point of ingress.

App Mesh Ingress Gateway supports 
a) [Amazon Application Load Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/introduction.html), which is required for traffic ingress into EKS Fargate nodes but can also be used with Pods on regular EC2 EKS nodes, and 
b) [Amazon NLB](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/introduction.html) (more testing needed) currently compatible only with EKS EC2 nodes.

All Kubernetes namespaces that should have their GatewayRoutes handled by the gateway, should be labeled with:
```yaml
  gateway: <GATEWAY NAME>
```

