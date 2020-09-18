This is a very simple Helm Chart for adding AWS App Mesh to an EKS Kubernetes cluster.

To prepare an AWS EKS cluster for adding an App Mesh by adding appropriate CRDs and installing App Mesh Controller, please run this PowerShell script:
https://github.com/vgribok/AWS-PowerShell-Shortcuts/blob/master/src/App-Mesh-Controller-EKS-Installer.ps1

This chart adds the App Mesh via a Kubernetes resource, resulting in corresponding App Mesh resource also created at AWS.

Each Kubernetes **namespace** that will be a part of the mesh should be given following **labels**:
```yaml
  mesh: <MESH NAME>
  appmesh.k8s.aws/sidecarInjectorWebhook: enabled
```

## Command line examples

## Failure: All defaults

```PowerShell
helm upgrade -i --dry-run `
 app-mesh `
 ./chart
```

The output should be an error message about the missing mesh name.

## Happy path

```PowerShell
helm upgrade -i --dry-run `
 --set appMesh.name=some-name-for-the-mesh `
 app-mesh `
 ./chart
```
