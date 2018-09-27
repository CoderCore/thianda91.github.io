---
layout:       article
title:        互联网技术 第四、五、六章
key:          2018-09-19
tags:         internet
categories:   internet
date:         2018-09-19 22:55:35 +08:00:00
modify_date:  2018-09-21 11:21:16
---

《互联网技术》教材 内容节选

<!--more-->

## 第4章 网络操作系统

Network Operating System，NOS。

### 4.1 网络操作系统的功能

单机操作系统功能：进程管理、存储管理、文件系统和设备管理。

网络操作系统功能：上述功能，以及，网络通信、共享资源管理、网络管理、网络服务、互操作、提供网络接口

单机操作系统特性：并发、资源共享、虚拟和异步。

网络操作系统特性：上述特性，以及，开放性、一致性、透明性。

安全性：用户账号安全性、时间限制、站点限制、磁盘空间限制、传输介质的安全性、加密、审计。

#### 4.1.3 逻辑构成

- 网络环境软件：多任务软件、传输协议软件、多用户文件系统形成软件。
- 网络管理软件：安全性管理软件、容错管理软件、备份软件、性能检测软件。
- 工作站网络软件：重定向程序、网络基本输入/输出系统
- 网络服务软件：多用户文件服务软件、名字服务软件、打印服务软件、电子邮件服务软件。

局域网 NOS 分层结构：网络驱动程序、网络协议软件、应用程序接口软件。

### 4.2 Windows 系列操作系统

### 4.3 Unix 操作系统

20 世纪 60 年代后期，一些程序员希望能够与程序进行交互式的工作，并使用一种尽可能少地对程序员强加结构限制的系统。

特性：

- 具有支持多个同时登录的用户的能力，是真正的多用户系统。
- 合并可卸下卷的层次文件系统。
- 文件、设备和进程输入/输出具有一致的接口。
- 可在后台开始进程。
- 有上百个子系统，包括几十种程序设计语言。
- 程序的源代码具有可一直性。
- 用户定义的窗口系统。

结构：内核（Kernel）、Shell、文件系统。

网络文件系统（Net File System，NFS）。

### 4.4 Linux 操作系统

Linux 操作系统是 UNIX 操作系统在微机上的实现。从一开始是一个编程爱好者的系统，它的出发点是核心程序的开发，而不是对用户系统的支持。

## 第5章 交换技术

### 5.1 交换机的数据转发

### 5.2 VLAN 技术

划分标准：

- 基于端口划分
- 基于 MAC 地址划分
- 基于网络层划分
- 基于 IP 多播划分
- 基于策略划分
- 基于用户定义、非用户授权划分

VLAN 之间通信的方式：

- MAC 地址静态登记
- 帧标签
- 虚连接
- 路由方式

VLAN 交换机互联的方式：

- 接入链路，access link
- 中继链路，trunk link
- 混合链路，hybrid link

### 5.3 多层交换技术

3 层交换，在 2 层基础上引入 3 层交换功能的机制。也成 IP 交换技术。

4 层交换，传输层，依据 TCP / UDP 应用端口号。真正的“会话交换机”。

7 层交换，又称智能交换，以内容为主的交换技术，根据内容进行负载均衡，也被看成是“应用交换技术”。

### 5.4 CDN 技术

内容分发网络（Content Delivery Network，CDN），是构建在基础 IP 承载网络之上，面向流媒体、Web 及应用的内容传输，具备内容自动化分布及流量集中化调度控制能力的叠加网络。CDN 由分布在不通区域的 CDN 节点组成，通过全局负载均衡的调度机制和内容中心的分发机制实现签约内容源的请求调度和内容缓存。CDN 按照制定策略将签约内容分发至网络边缘，并自动调度用户内容访问请求指向全局最优的边缘节点，由该边缘节点就近为用户提供内容服务，使用户可以通过访问就近的 CDN 节点获取内容源。

这里有一篇[更详细的文章](../notes/content-deliver-network.html)。

#### 5.4.1 CDN 体系架构

**逻辑架构**：调度控制层、内容中心层、服务节点层。

**功能组件**

调度控制层：

- 运营管理中心。业务管理、网络管理、策略管理、运营分析、客户服务。
- 调度控制中心。用户请求调度、调度策略管理、节点状态管理、内容视图管理。

内容中心层：

内容注入、内容定位、内容管理、内容删除、内容分发、内容处理、内容存储。

服务节点层：

本地调度、内容分发、内容缓存、内容服务。

**CDN 外围系统**

- 业务系统：内容管理系统、内容源。
- Local DNS
- 用户终端
- 营账系统：CDN 业务线上订购。
- 数据网管系统：获取承载网络拓扑和链路状态等，对 CDN 性能、故障、安全进行管理和监控。
- 日志留存系统：按照工信部的相关要求
- 信息安全管理系统
- 其他系统：灵活接入其他外部网元，提供业务管理、用户管理、业务功能等拓展。

#### 5.4.2 CDN 网络架构

分层、分布式部署。在全国骨干网节点部署全局调度控制中心、区域调度中心、运营管理中心，以及全网内容中心。在省网核心节点部署区域调度中心、升级内容中心/区域缓存节点。在城域骨干节点部署边缘服务节点，根据业务规模在城域网核心层、业务控制层、汇聚层采用分级部署方式。

CDN 可分为控制平台和数据平台。

调度机制：可参考教程书籍的 101 页，PDF 的 109 页。

### 5.5 SDN 技术

软件定义网络（Software Defined Networking，SDN）。

特点：控制和转发分离，支持集中化的网络状态控制，底层网络设施对上层应用透明。

基本特征

- 控制和转发分离
- 网络业务可编程
- 集中化控制

体系架构：应用层、控制层、基础设施层。

应用层的北向接口与控制层连接。控制层的南向接口与基础设施层连接。

> 北向接口：被管理。提供给其他厂家或运营商进行接入和管理的接口，即向上提供的接口。
> 南向接口：管理。管理其他厂家网管或设备的接口，即向下提供的接口。

优势：

- 将网络协议集中处理，有利于提高复杂协议的运算效率和收敛速度。
- 控制的集中化有利于从更宏观的角度调配传输带宽等网络资源，提高资源的利用率。
- 简化了运维管理的工作量，提高运维效率，大幅节省运维费用。
- 通过 SDN 可编程性，工程师可以在一个底层物理基础设施上家在多个虚拟网络，然后使用 SDN 控制器分别为每个网段实现 QoS 保证，从而增加了差异化服务的程度和灵活性。
- 业务定制的软件化有利于新业务的测试和快速部署。
- 控制与转发分离，实施控制策略软件化，有利于网络的智能化、自动化和硬件的标准化。

随选网络：敏捷、简单、灵活、可靠。

## 第6章 网络安全

计算机安全

目的在于实现信息系统资源的完整性、可用性，以及机密性（包括硬件、软件、固件、信息/数据、电信）。

常提及的还有：真实性、可计量性。

网络安全的实现：网络安全技术、安全管理、安全教育、法律法规。

安全攻击

被动攻击防范：检测。主动攻击防范：物理保护。

### 6.2 密码学(略)

### 6.3 网络安全应用(略)

### 6.4 系统安全

#### 6.4.3 防火墙

6 种基本类型

- 包过滤型
- 代理服务器型
- 电路蹭网关
- 混合型
- 应用层网关
- 自适应代理技术
