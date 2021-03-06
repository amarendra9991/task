#Deploy Kubernetes Clusters on AWS using Terraform and Terraform RKE Provider

# Requirements

    terraform
    Valid AWS access_key and secret_key
    kubectl command

#Deploy Kubernetes Cluster on AWS

#clone this repo
$ git clone https://github.com/amarendra9991/task.git
$ cd c:/temp/aws_ec2

#set API keys to environment variables

$ export AWS_ACCESS_KEY_ID="AKIASPBBW3WKPXL4CCNA"
$ export AWS_SECRET_ACCESS_KEY="xxxxxxxxxxxxxxxx"

#deploy
$ terraform init && terraform apply

#set KUBECONFIG environment variable for kubectl
$ export KUBECONFIG=${PWD}/kube_config_cluster.yml


$ kubectl get cs

NAME                 STATUS    MESSAGE              ERROR
controller-manager   Healthy   ok                   
scheduler            Healthy   ok                   
etcd-0               Healthy   {"health": "true"}  

#nodes
$ kubectl get nodes

NAME                                             STATUS    ROLES               AGE       VERSION
ip-xx-xx-xx-xx.ap-northeast-1.compute.internal   Ready     controlplane,etcd   1m        v1.10.1
ip-xx-xx-xx-xx.ap-northeast-1.compute.internal   Ready     worker              1m        v1.10.1
ip-xx-xx-xx-xx.ap-northeast-1.compute.internal   Ready     worker              1m        v1.10.1
ip-xx-xx-xx-xx.ap-northeast-1.compute.internal   Ready     worker              1m        v1.10.1
