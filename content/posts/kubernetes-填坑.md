---
title: "kubernetes填坑"
date: 2018-10-21T22:00:00+800
draft: false

### 硬盘不够不够
minikube start --vm-driver hyperkit --disk-size 10g

### 卡在Starting cluster components不动
>  使用v0.24.1版本。命令如下：

```bash
curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.24.1/minikube-darwin-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/
```

