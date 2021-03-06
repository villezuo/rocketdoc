---
layout: default
id: Routing
title: 路由
---

## 路由

Rocket应用程序以路由`routes`和处理程序`handlers`为中心。路由包括：

- 与传入请求匹配的一组参数。
- 处理请求并返回响应的处理程序。

处理程序只是一个函数，它接受任意数量的参数并返回任意类型。

要匹配的参数包括静态路径、动态路径、路径段、表单、查询字符串、请求格式说明符和正文数据。Rocket使用类似于其他语言中的函数装饰器的属性来简化声明路由。路由是通过注释一个函数即处理程序来声明的，该函数的参数集与之匹配。完整的路由声明如下：

```rust
#[get("/world")]              // <- 路由属性
fn world() -> &'static str {  // <- 请求处理程序
    "Hello, world!"
}
```

这个`word`路由声明将与传入GET请求的静态路径`“/world”`匹配。`world`路由很简单，但是在构建更有趣的应用程序时，需要附加路由参数。“[请求 Requests](/rocketdoc/Requests/Methods.html)” 部分描述了用于构造路由的可用选项。