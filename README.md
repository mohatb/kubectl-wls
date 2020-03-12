# kubectl-wls:
kubectl-wls is an interactive shell script and kubectl plugin that allows you to access a kubernetes windows or linux nodes.

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
wget https://github.com/mohatb/kubectl-wls/raw/master/kubectl-wls

chmod +x ./kubectl-wls

sudo mv ./kubectl-wls /usr/local/bin/kubectl-wls
```

# Usage:
```
Interactive:
$ kubectl-wls

Non-Interactive
$ kubectl-wls NODE
```
