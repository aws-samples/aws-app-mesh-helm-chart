# Summary

Installs App Mesh Ingress Gateway on an EKS cluster, enabling usage of. 

All Kubernetes namespaces that should have their GatewayRoutes handled by the gateway, should be labeled with:
```yaml
  gateway: <GATEWAY NAME>
```

