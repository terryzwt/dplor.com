---
title: fish shell小技巧
date: 2018-09-19T13:26+08:00
draft: false
---

### 问题
使用[fish shell](http://fishshell.com)替代系统的bash，可以带来更好的使用体验和效率提升。但是fish shell也提出了自己的工作方式，有些是和bash不兼容的，比如export命令。这里记录一些常用的转换方式。

#### 环境变量设置问题：
* bash
```bash
export PATH=$PATH:/your-path
```

* fish
```bash
set -x PATH $PATH /your-path
```

#### alias设置：
* bash > ~/.bashrc \| ~/.bash_profile
```bash
alias vi="nvim"
```

* fish > ~/.config/fish/config.fish
```bash
alias vi="nvim"
```

### 参考链接
- https://zhuanlan.zhihu.com/p/26157081
