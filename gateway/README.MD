# Summary

Installs App Mesh VirtualGateway on an EKS Fargate cluster. Before running, please ensure an app mesh is already created.

After VirtualGateway is created, all Kubernetes namespaces that should have their GatewayRoutes handled by the new gateway, should be labeled with:
```yaml
  gateway: <GATEWAY NAME>
```

More details TBD.