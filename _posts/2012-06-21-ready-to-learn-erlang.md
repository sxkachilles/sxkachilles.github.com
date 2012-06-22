---
layout: post
title: 准备学习 Erlang
tags: [Erlang]
---

# Why Erlang？
* 大型系统，必须考虑容错、分布、负载均衡

* 单核频率提升而带来的软件自动加速时代已经终结，性能的免费午餐已经不复存在，必须考虑利用多核心提高程序效能

* 传统并行编程模型中的锁、同步、线程、信号量不仅未必能实现程序效能的提升，而且使用这些复杂的机制也成了程序员的噩梦

* Erlang 采用消息模型（Actor），不使用共享数据的线程，而使用尽可能轻量级的进程（lightweight process），从根本上避免了锁

* Erlang 在语言级别提供了一系列并发原语，提出了新的编程模型——面向并发编程（COP）

* Erlang 假设程序难免出错，让出错的进程直接退出而不尝试自行处理，由高级进程来处理错误，支持不停机系统维护，从而非常容易构建高容错高可靠的大型应用程序

# What is Erlang？
* 支持 FP 和 COP

* 基于虚拟机 BEAM，编译的结果是字节码；BEAM 上已经开始有其他语言运行

* 提供一个 Shell 解释器

* 成熟的工业应用以及成熟的库 OTP(Open Telecom Platform)：行为（Behavior）-比如 gen_server

* 有一个全球软件仓库 CEAN

* Erlang 除了用于电信系统提供了超高的容错以外，还是构建 CouchDB 和 Facebook Chat 的语言

# vs Scala
* Scala 的设计初衷是基于 JVM 及其生态系统，整合 OOP 和 FP，替代已显老态的 Java 语言，后来引入了 Actor 模型着力解决多核危机，但在可靠性上，并没有 Erlang 所具有的固有优势

* Scala 是一个静态类型语言，而 Erlang 是动态类型的

* Scala 可以选择数据不变性，而 Erlang 是强制数据不变性的（本质上是函数式编程语言）

* 在互联网领域 Scala 的应用比 Erlang 活跃，StackOverflow 和 Github 都印证了这一点，尤其 Twitter 使用 Ruby + Scala 的架构推动了 Scala 在开源社区中的发展

