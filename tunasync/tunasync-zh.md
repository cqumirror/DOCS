---
author: weearc(Binye Qi)
date: 2020.01.11
---

# 前言

我撰写这个文档的原因仅仅是因为在某次镜像同步故障以后翻了很久 tunasync 的 issue，文档以后都没有找到解决方案，最后从源代码窥见倪端，浪费了大量的时间和精力，也让我意识到了不能总是依赖着现有的这些解决方案：我们终将构建属于我们自己的合适的同步工具以及镜像站前端，并应该在构建的同时建立一个非常完善的文档，绝不想让再一个人体会到干找找不到解决方案的痛苦。

因此本文尽可能的从**快速上手**的角度来对 tunasync 工具包进行说明。

# 开始使用

## Tunasync 是什么

tunasync 是一个强大的、提供给镜像站管理员的镜像统一管理工具。目前重庆大学开源软件镜像站使用的是 tunasync 0.33 。

整个工具包分为两个部分：

- tunasync
- tunasynctl

## 前序准备工作

如果熟悉 Linux 我相信你应该更容易对这个工具上手，这里我假设你对 Linux 相对熟悉，知道如何进行一般的操作，有安全意识。

这里你需要准备的是：

- 一台可以访问网路的计算机 / 伺服器（需要安装好操作系统。比如 Ubuntu 或者CentOS）
- Xshell 或者 putty 或者 *Unix 下的一个终端，我相信一般都会预装 ssh 工具的。
- rsync

你需要访问 TUNA 的 GITHUB 仓库，找到 tunasync 仓库的`release` 页进行下载。并使用 sftp 或其他方式上传到你的伺服器上（当然如果网路条件非常好建议直接在伺服器上进行下载）。

rsync 可以从软件源直接进行安装。

接下来你需要准备一下配置文件了。

### 配置文件

#### manager.conf

#### worker.conf

### 功能说明以及示例

#### tunasync

tunasync 一般能用到的就只有一下两条指令：

```bash
#启动 tunasync manager
/path/to/file/tunasync  manager -config  /path/to/file/manager.conf
#启动 tunasync worker
/path/to/file/tunasync  worker -config  /path/to/file/worker.conf
```

可以直接放在 tmux session 中，不用管它。

#### tunasynctl

tunasynctl 才是整个工具中最重要的部分，也是一不小心就不停踩坑的部分。

主要指令的格式：

```bash
/path/to/file/tunasynctl  [操作]   [对象（一般是镜像）]  -w [worker的名称]
```





# 高级使用

## 从源代码构建

