---
title: "kubernetes填坑"
date: 2018-10-21T22:00:00+08:00
draft: false
---

### 硬盘不够不够
minikube start --vm-driver hyperkit --disk-size 10g

### 卡在Starting cluster components不动
>  使用v0.24.1版本。命令如下：

```bash
curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.24.1/minikube-darwin-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/
```

### 和minikube 0.24.1配套的kubectl安装
[参考](https://github.com/kubernetes/kubernetes/issues/65575#issuecomment-414666732)
```bash
brew install https://raw.githubusercontent.com/Homebrew/homebrew-core/d09d97241b17a5e02a25fc51fc56e2a5de74501c/Formula/kubernetes-cli.rb
brew switch kubernetes-cli 1.10.5
```
