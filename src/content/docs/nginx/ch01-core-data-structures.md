---
title: 第一章 · 核心数据结构
description: '深入剖析 Nginx 中最核心的内存池 ngx_pool_t 与数组 ngx_array_t 的实现'
order: 2
---

## ngx_pool_t — 内存池

Nginx 几乎所有内存分配都通过内存池完成，避免频繁的 malloc/free 调用，同时统一管理内存生命周期。

### 数据结构

```c
typedef struct ngx_pool_s  ngx_pool_t;

struct ngx_pool_s {
    ngx_pool_data_t       d;
    size_t                max;
    ngx_pool_t           *current;
    ngx_chain_t          *chain;
    ngx_pool_large_t     *large;
    ngx_pool_cleanup_t   *cleanup;
    ngx_log_t            *log;
};
```

关键点：

- `d` — 内存池数据区，包含小块内存链表
- `max` — 小块内存的最大字节数（超过则分配大块内存）
- `current` — 指向可分配的空闲节点
- `large` — 大块内存链表
- `cleanup` — 清理回调链表

### 内存分配流程

（待补充...）

## ngx_array_t — 动态数组

（待补充...）

## 总结

（待补充...）
