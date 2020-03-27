# rook ceph multi clusters

This example shows how to setup two instances of `CephCluster`, each with `replica` set to 2 and exposing two different `StorageClass` resources.

Namespaces are arranged as follows:

*Operator* runs in the `rook-ceph` namespace.

*CephCluster* for data (backed by low performance disks) runs in the `rook-ceph-data` namespace. 

*CephCluster* for index (backed by faster disks) runs in the `rook-ceph-idx` namespace.

## Kustomize

The example provide kustomization files with 2 overlays

### dev overlay

This is a 3 nodes setup, with disks selected by `devicePathFilter` property.

Render with:
`kustomize build rook-ceph/overlays/dev`

### production overlay

This is a 3 nodes setup, with disks selected by  deviceFilter property.

Render with:
`kustomize build rook-ceph/overlays/production`
