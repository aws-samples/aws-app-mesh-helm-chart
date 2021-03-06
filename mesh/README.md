This is a [very simple](../mesh/chart/templates/mesh.yaml) Helm Chart for adding AWS App Mesh to an Amazon Elastic Kubernetes Service (EKS) cluster.

To prepare an AWS EKS cluster for adding an App Mesh by adding appropriate CRDs and installing App Mesh Controller, please run [this PowerShell script](https://github.com/aws-samples/eks-powershell-shortcuts/blob/main/src/App-Mesh-Controller-EKS-Installer.ps1):

This chart adds the App Mesh via a Kubernetes resource, resulting in corresponding App Mesh resource also created at AWS.

Each Kubernetes **namespace** that will be a part of the mesh should be given following **labels**:
```yaml
  mesh: <MESH NAME>
  appmesh.k8s.aws/sidecarInjectorWebhook: enabled
```

