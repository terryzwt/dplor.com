### 问题
在MAC下，使用docker-machine跑的虚拟机，使用docker-machine-nfs加速，在docker-machine上面跑的docker，运行一段时间后，发现docker时间变慢了。
通过docker machine运行的虚拟机的时间也变慢了。

### 解决
```bash
docker-machine ssh default
sudo ntpclient -s -h pool.ntp.org
```
### 参考：
https://stackoverflow.com/questions/24551592/how-to-make-sure-dockers-time-syncs-with-that-of-the-host
