# [0008. 使用 ctx.lineCap 设置线条端点样式](https://github.com/Tdahuyou/TNotes.canvas/tree/main/notes/0008.%20%E4%BD%BF%E7%94%A8%20ctx.lineCap%20%E8%AE%BE%E7%BD%AE%E7%BA%BF%E6%9D%A1%E7%AB%AF%E7%82%B9%E6%A0%B7%E5%BC%8F)

<!-- region:toc -->

- [1. 📝 概述](#1--概述)
- [2. 💻 demos.1 - 线条端点样式](#2--demos1---线条端点样式)

<!-- endregion:toc -->

## 1. 📝 概述

- 🎯 目标
  - 学会使用 `ctx.lineCap` 来设置线条端点样式
- 🫧 评价
  - 非常简单的一个属性，line 表示线条、cap 表示端点（帽子），lineCap 就是用来设置线条端点（线帽）的样式的。
  - 需要知道线帽的类型都有：butt（默认值） | round | square
  - 需要注意的是，如果加上线帽（round、square），会导致线条变长。
    - 多出的这部分长度，就是左右两端线帽的长度。
    - 每一侧多出的长度是可以计算的，结果是：线条的宽度 `lineWidth / 2`。

## 2. 💻 demos.1 - 线条端点样式

::: code-group

<<< ./demos/1/1.html {16-51}

:::

- 端点会在原线条的基础上往外延伸一段距离，这段距离取决于线条的宽度 `ctx.lineWidth` 的值。
  - 在线条的左侧和右侧分别会多出一个宽度为 `ctx.lineWidth / 2` 的 `lineCap` 线帽
- 最终效果：
  - ![img](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-10-03-23-06-25.png)
