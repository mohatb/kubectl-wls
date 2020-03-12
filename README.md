# kubectl-wls:
kubectl-wls is a shell script that allows you to get into a node shell.

# How it works ?

It works by creating a pod (with a priviledged container) in the node you specified and using nsenter http://man7.org/linux/man-pages/man1/nsenter.1.html for getting a shell into your kuberntes nodes.

The created pod is from alpine official image which is ~2.6 mb in size, once you exit the shell, the pod will be deleted.

# For Windows Nodes:

It is required to have OpenSSH on windows, with credentials user/pass. SSH keys are currently not supported but will be added soon/

https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse

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
