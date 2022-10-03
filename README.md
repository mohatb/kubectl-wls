> Warining: This repo is deprecated and all the work/development will continue on https://github.com/mohatb/kubectl-exec

# kubectl-wls:
kubectl-wls stands for kubectl Kubectl-Windows-Linux-Shell, it is an interactive shell script and also a kubectl plugin that allows you to access a kubernetes windows or linux nodes shell.

# How it works ?

For Linux Nodes:

It works by creating a pod (with a priviledged container) in the node you specified and using nsenter http://man7.org/linux/man-pages/man1/nsenter.1.html for getting a shell into your linux nodes.


For Windows Nodes:

It is required to have OpenSSH on windows, with user/pass credentials. SSH keys are currently not supported but will be added soon.

To Install OpenSSH on your windows nodes, please follow the below:
https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse

Since windows images are large in size, kubectl-wls will create a linux image on a linux node and establish an SSH connection to the windows node.

Note: AKS nodes have OpenSSH installed by default.


# Installation:
```
wget https://raw.githubusercontent.com/mohatb/kubectl-wls/master/kubectl-wls

chmod +x ./kubectl-wls

sudo mv ./kubectl-wls /usr/local/bin/kubectl-wls
```

# Usage:
```
Interavtive
$ kubectl-wls
 
Non-Interactive
$ kubectl-wls NODE
 
Create a mount pod that can be used to transfer data between node and local
$ kubectl-wls -mount
 
Examples:
kubectl-wls
kubectl-wls minikube
kubectl-wls -mount
kubectl-wls -mount node1
```
