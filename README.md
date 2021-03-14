# Microk8s + Rook + Ceph

## Prerequisite

```bash
$ git clone --single-branch --branch v1.5.8 https://github.com/rook/rook.git
$ cp operator.yaml rook/cluster/examples/kubernetes/ceph/
$ cp cluster.yaml rook/cluster/examples/kubernetes/ceph/
# copy common.yaml only if you want to disable hostNetwork
$ cp common.yaml rook/cluster/examples/kubernetes/ceph/
```

## Install

```bash
$ cd rook/cluster/examples/kubernetes/ceph/
$ kubectl create -f crds.yaml -f common.yaml -f operator.yaml
## verify the rook-ceph-operator is in the `Running` state before proceeding
$ kubectl create -f cluster.yaml
```

### Configure storage

- [Block](https://rook.io/docs/rook/v1.5/ceph-block.html)
- [Object](https://rook.io/docs/rook/v1.5/ceph-object.html)
- [Shared Filesystem](https://rook.io/docs/rook/v1.5/ceph-filesystem.html)

## References

- https://rook.io/docs/rook/v1.5/ceph-quickstart.html
- https://rook.io/docs/rook/v1.5/ceph-quickstart.html#deploy-the-rook-operator
- https://github.com/rook/rook/blob/master/Documentation/ceph-cluster-crd.md
