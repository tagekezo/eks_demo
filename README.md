#### Install kubectl
https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html

#### Install eksctl
https://docs.aws.amazon.com/eks/latest/userguide/eksctl.html

#### Install helm
https://docs.aws.amazon.com/eks/latest/userguide/helm.html

#### Setup aws access keys
https://docs.aws.amazon.com/powershell/latest/userguide/pstools-appendix-sign-up.html
https://docs.aws.amazon.com/powershell/latest/userguide/specifying-your-aws-credentials.html

#### Create ec2 key pair
```
aws ec2 create-key-pair --region ap-southeast-1 --key-name test
```

#### Create eks cluster
```
eksctl create cluster \
--name eks-demo \
--region ap-southeast-1 \
--with-oidc \
--ssh-access \
--ssh-public-key test \
--managed
```

#### Verify eks cluster nodes are created
```
kubectl get nodes -o wide
```

#### Install helm chart
Templates are referenced from https://kubernetes.io/docs/tutorials/stateless-application/guestbook/
```
helm install gbchart gbchart
```

#### Verify helm chart is deployed
```
helm list
```

#### Verify all pods, deployments and services are created
```
kubectl get pods --output=wide
kubectl get deployments
kubectl get services
```

#### Scale frontend pods
```
kubectl scale deployment frontend --replicas=5
```


