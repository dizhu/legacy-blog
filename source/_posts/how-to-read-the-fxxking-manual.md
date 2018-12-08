---
title: 如何读文档？
date: 2017-07-16 21:57:12
tags: [编程, Ruby]
---

## 前言

今天收到一份微博私信，问我之前 [量产型炮灰工程师](/2017/05/22/mass-produced-engineers/) 中说一个良性的学习循环需要自己寻找线上资源学习、读文档等等，这些都没有在培训班中被学到。那怎样才能比较好的读文档呢？不分享一下的话，老说我是光破不立，光批评别人自己却没有任何解决。那么我来分享一下我读文档的思路吧。

## 大局入手

首先，这里的读文档并不局限于接口文档，接口文档更像是工具书，这里的文档泛指围绕代码周边的文字说明。你要学习一门语言、框架或者某个工具，肯定不是因为它是一个工具所以你就学。框架的开发者也不会是因为想写一个框架所以就写一个框架。凡事都一定有它的理由，一个语言、框架、工具的存在一定是为了解决某一个或某一类特定的问题而存在的。同一个类型的不同的语言、框架、工具之所以会不同，是因为他们试图在解决不同的问题，或者某个工具正在解决另一个不能解决的某种问题。这时候作者的想法是尤为重要的，如果弄清楚这方面想法对于你的学习自然是事半功倍的。

作者的想法在哪里？

在官方的教程、官方的概述里。对于 Ruby 来说，其官网的[关于页](https://www.ruby-lang.org/zh_cn/about/)短短一页就几乎解释了什么是 Ruby，Ruby 和其他语言的不同：

- Ruby 从多门语言中学习了经验，注重其平衡性
- 兼具函数式编程和命令式编程特色
- Ruby 试着让语言更自然，而不是更简单
- Ruby 将一切视为对象
- Ruby 允许用户修改语言自身
- Ruby 的闭包具有极强表现力
- Ruby 对象只提供单继承，但支持混入
- Ruby 的变量系统
- Ruby 的其他细节

有了这些大纲，这对于你理解 Ruby 中的很多表现就有了很大的认识。接着再去看 Ruby User's Guide 或者 Programming Ruby 就会有很大的帮助。

## 了解变化

在学习了一个东西的大纲和入门教程之后，大版本的更新记录是文档中非常重要，却是最容易被忽略的部分。

比如 Qt 在 4.8 版本中引入了 QML。我相信很多公司都号称使用 Qt 做跨平台界面开发，却很少注意 Qt 本身的变化。很多公司 Qt 5 的代码写得和 Qt 3 也没有什么区别。QML 的引入对于界面的绘制，事件的绑定和数据的刷新提供了一整套 DSL，从而让整个开发变得容易和可读太多。大版本的更新记录很重要是因为之所以会有版本更新一定是因为之前写的不好，需要改进。如果只是从细节入手看接口，旧接口通常会为了兼容性而保留，这时候并不能宏观地知道作者想让你怎么用。

比如 Ruby 在 2.3.0 中引入了 Safe Navigation Operator `&.`，其类似于 C# 中的 `?.`。Ruby 的 ActiveSupport 库中本来其实有类似的语法，它是 `Object#try`。但 Ruby 作者将这个东西从一个语义层面提升到了一个语法层面，体现了作者在这方面的重视。这是 Ruby 所说的 `注重其平衡性` 的一种体现。当你了解了作者的这种想法，你才能写出更好的代码，显然 Ruby 作者对 Ruby 的理解是相当深刻的。

再比如 HTML5 中引入了 WebSocket API，显然就是来解决 Web 双工实时通讯的问题的。如果放着这样的 API 不用，还在使用轮询，甚至在浏览器上做一些 tricks 来实现更长的连接，不但是浪费资源，更是浪费自己的精力。

## 实践与细节

了解了框架的设计思路，了解了基本的使用方法，接下来才可以看接口文档。这时候你已经有了对框架的基本理解，你就知道自己需要看什么。可以结合一个自己要做的项目边写边看。需要用到什么具体的模块，就去查这个模块的所有 API。这通常查询起来会比较方便。当然光看 API 文档只是对框架的使用，还是不够的。一个好的项目不只是使用的优雅，更是管理的艺术。项目要管理得好更需要对项目做正确的抽象，这时候再去多看看这个框架的一些好的项目的开源实现，学习一下。之后就对整个框架不仅仅是熟悉使用了，更是有了大局上的认知，使用起来比单纯熟悉语法要好很多。

看别人的代码的思路其实和看文档是一样的，不要从细节入手，只会让自己「乱花渐欲迷人眼」。从大局入手，了解作者的实现思路，然后找出实现的最主要的抽象的部分，再慢慢去啃细节的实现自然会比一行一行读容易许多。

## 最重要的是

写代码不是默写，没有人不让你边写边搜边找。读文档的关键是要在出了问题后知道自己要找什么，去哪里找。学习不是闭门造车，要多培养自学的能力，是为了让自己在脱离别人的教学之后知道自己怎么学，去哪里学。计算机软件行业是一个快速更迭的行业，只有让自己始终在学习，才能不至于在这个行业中落后。