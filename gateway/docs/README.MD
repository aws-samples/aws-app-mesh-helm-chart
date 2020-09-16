# Command line examples

## Failure: all defaults

```PowerShell
helm upgrade -i --dry-run `
 app-mesh-gateway `
 ./chart
```

The output should be an error message about missing AWS Region value.

## Failure: missing mesh ARN

```PowerShell
helm upgrade -i --dry-run `
 --set image.awsRegion=us-east-2 `
 app-mesh-gateway `
 ./chart
```

The output should be an error message about missing App Mesh ARN.

## Bare minimum with No Fargate and with NLB ingress

```PowerShell
helm upgrade -i --dry-run `
 --set image.awsRegion=us-east-2 `
 --set appMesh.arn=arn:aws:appmesh:us-east-2:123456789012:mesh/my-mesh `
 app-mesh-gateway `
 ./chart
```

The output will be a manifest with a Deployment, a Service of a LoadBalancer type, and a VirtualGateway.

## Failure with Fargate on, but without Pod serviceAccount

```PowerShell
helm upgrade -i --dry-run `
 --set image.awsRegion=us-east-2 `
 --set appMesh.arn=arn:aws:appmesh:us-east-2:123456789012:mesh/my-mesh `
 --set ingress.fargate=true `
 app-mesh-gateway `
 ./chart
```

The output should be an error message about missing fargatePodServiceAccount parameter value.

## Gateway with Fargate and ALB based Ingress

```PowerShell
helm upgrade -i --dry-run `
 --set image.awsRegion=us-east-2 `
 --set appMesh.arn=arn:aws:appmesh:us-east-2:123456789012:mesh/my-mesh `
 --set ingress.fargate=true `
 --set appMesh.fargatePodServiceAccount=envoy-pod-serviceaccount `
 app-mesh-gateway `
 ./chart
```
The output will be a manifest with a Deployment, a Service of a ClusterIP type, a VirtualGateway and an Ingress routing traffic to the Service.