# Helm Charts for creating AWS App Mesh and its Gateway Controller

1. Please create an [App Mesh](./mesh/README.md) first.
2. Create new or choose existing Kubernetes namespace and mark it for App Mesh with "`mesh: <MESH NAME>`" label.
3. Then install [App Mesh Gateway Controller](./gateway/README.MD) in the meshed namespace from the step 2.

