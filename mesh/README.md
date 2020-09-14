This is a very simple Helm Chart for adding AWS App Mesh to an EKS Kubernetes cluster.

To prepare an AWS EKS cluster for adding an App Mesh by adding appropriate CRDs and installing App Mesh Controller, please run this PowerShell script:
https://gist.github.com/vgribok/0e656bcc296375ad7db839b2a025a183

This chart adds the App Mesh via a Kubernetes resource, resulting in corresponding App Mesh resource also create at AWS.