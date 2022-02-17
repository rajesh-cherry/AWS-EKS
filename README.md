# AWS-EKS
Prerequisties

1. AWS CLI Access with admin Privileges.
2. one instance (AWS Cli Must have installed)
3. SSH key (optional) when you are going to allow remote Access to worker node if not we can ignore it.

Steps Involved

Step 1 : Install EKSctl and kubectl utility

step 2 : Create EKS Cluster Using EKSctl utility

Step 3 : Deploying Demo Application (we will deploy and demo application on top of the eks cluster)

check eksctl command is working or not if command not found download EKSCtl)

```bash
eksctl
```

Download EKSCtl (https://docs.aws.amazon.com/eks/latest/userguide/eksctl.html)

move eksctl to usr/local/bin location

```bash
sudo mv /eksctl /usr/local/bin
```

check the command again

```bash
eksctl version
```
check kubectl command is working or not, if command not found download kubectl
```bash
kubectl
```

Download Kubectl (https://kubernetes.io/docs/tasks/tools/)

make it executable by using command 

```bash
Chmod +x ./kubectl
```
Move the kubectl to bin location

```bash
# mkdir -p $Home/bin && cp ./kubectl $HOME /bin/kubectl && export PATH=$PATH:$HOME/bin
```
check the command again
```bash
kubectl version
kubectl version --client
```
It will list the client version details but not the server version for that
we should have the EKSCluster ready

Download and install AWS-Cli (https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
AWS CLI is used to manage aws-services

```bash
aws configure
```
Let's create the EKSCluster but before that if you want to allow remote access to the worker nodes then you should have the ssh-key ready (optional)

```bash
eksctl create cluster --name test --region ap-south-1 --nodegroup-name eks-demo --node-type t2.micro --nodes-min 2 --nodes-max 2
```
now wait for 15mins to create the cluster
