---
title: "docker-machine 填坑小记"
date: 2018-10-29T08:00:00+08:00
draft: false
---

<pre>
Running pre-create checks...
Creating machine...
(m1) Copying /Users/terry/.docker/machine/cache/boot2docker.iso to /Users/terry/.docker/machine/machines/m1/boot2docker.iso...
(m1) Creating VirtualBox VM...
(m1) Creating SSH key...
(m1) Starting the VM...
(m1) Check network to re-create if needed...
(m1) Waiting for an IP...
Waiting for machine to be running, this may take a few minutes...
Detecting operating system of created instance...
Waiting for SSH to be available...
Detecting the provisioner...
Provisioning with boot2docker...
Copying certs to the local machine directory...
Copying certs to the remote machine...
Setting Docker configuration on the remote daemon...

This machine has been allocated an IP address, but Docker Machine could not
reach it successfully.

SSH for the machine should still work, but connecting to exposed ports, such as
the Docker daemon port (usually <ip>:2376), may not work properly.

You may need to add the route manually, or use another related workaround.

This could be due to a VPN, proxy, or host file configuration issue.

You also might want to clear any VirtualBox host only interfaces you are not using.
Checking connection to Docker...
Error creating machine: Error checking the host: Error checking and/or regenerating the certs: There was an error validating certificates for host "192.168.99.101:2376": dial tcp 192.168.99.101:2376: i/o timeout
You can attempt to regenerate them using 'docker-machine regenerate-certs [name]'.
Be advised that this will trigger a Docker daemon restart which might stop running containers.
</pre>

docker-machine的IP ping不通。
通过如下命令解决，也就是重启网卡。

`
sudo ifconfig vboxnet0 down
sudo ifconfig vboxnet0 up
`

### 参考：

https://github.com/docker/machine/issues/4100
