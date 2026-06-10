---
title: 概述
description: 'Nginx 源码阅读笔记系列，记录从零开始研读 Nginx 源码的过程与心得'
order: 1
---

## 缘起

Nginx 作为高性能 Web 服务器的代表，其源码中蕴含了大量优秀的工程实践——精巧的内存管理、高效的事件驱动模型、模块化的架构设计。本系列笔记旨在通过逐行阅读 Nginx 源码，深入理解其设计思想与实现细节。

## 阅读路线

1. **核心数据结构** — ngx_pool_t、ngx_array_t、ngx_buf_t、ngx_list_t 等
2. **配置解析** — ngx_conf_t 体系，配置文件 → 内存结构的映射
3. **事件驱动模型** — epoll / kqueue 封装，连接处理流程
4. **HTTP 模块** — 请求解析、阶段处理、反向代理
5. **进程模型** — master-worker 架构、信号管理、热重启

## 环境

- 源码版本：基于 Nginx 主线分支
- 阅读工具：CLion + GDB
- 编译参数：`--with-debug` 开启调试支持

## 参考资料

- [Nginx 官方文档](https://nginx.org/en/docs/)
- 《深入理解 Nginx》— 陶辉
- [Nginx 开发从入门到精通](https://github.com/nginx/nginx)
