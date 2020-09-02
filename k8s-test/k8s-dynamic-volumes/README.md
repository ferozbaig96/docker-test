# Dynamic Volume Provisioning
This example shows how to create a EBS volume and consume it from container dynamically.
This example has been taken from https://github.com/kubernetes-sigs/aws-ebs-csi-driver/tree/master/examples/kubernetes
Check out different examples in the above link e.g. block-volume, resizing etc

## Prerequisites

1. Kubernetes 1.13+ (CSI 1.0).

1. The [aws-ebs-csi-driver driver](https://github.com/kubernetes-sigs/aws-ebs-csi-driver) is installed.
2. Make sure worker nodes has [relevant permissions](https://aws.amazon.com/premiumsupport/knowledge-center/eks-persistent-storage/)

## Usage

1. Create a sample app along with the StorageClass and the PersistentVolumeClaim:
```
kubectl apply -f specs/
```

2. Validate the volume was created and `volumeHandle` contains an EBS volumeID:
```
kubectl describe pv
```

3. Validate the pod successfully wrote data to the volume:
```
kubectl exec -it app cat /data/out.txt
```

4. Cleanup resources:
```
kubectl delete -f specs/
```

