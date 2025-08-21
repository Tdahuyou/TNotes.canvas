# [0009. 使用 ctx.lineDashOffset 设置虚线的偏移量](https://github.com/Tdahuyou/TNotes.canvas/tree/main/notes/0009.%20%E4%BD%BF%E7%94%A8%20ctx.lineDashOffset%20%E8%AE%BE%E7%BD%AE%E8%99%9A%E7%BA%BF%E7%9A%84%E5%81%8F%E7%A7%BB%E9%87%8F)

<!-- region:toc -->

- [1. 📝 概述](#1--概述)
- [2. 📒 `ctx.lineDashOffset`](#2--ctxlinedashoffset)
- [3. 💻 demos.1 - 使用 `ctx.lineDashOffset` 设置虚线的偏移量](#3--demos1---使用-ctxlinedashoffset-设置虚线的偏移量)

<!-- endregion:toc -->

## 1. 📝 概述

- 知识点：
  - 掌握 `ctx.lineDashOffset` 的基本使用
- 评价：
  - `ctx.lineDashOffset` 是用来设置线段的偏移方向的，值可以是正数或者负数，正负号决定了偏移的方向。
  - 类似这样改变位置的属性，往往都可以用来做动画效果。

## 2. 📒 `ctx.lineDashOffset`

- 动画
  - `lineDashOffset` 这个属性常用于实现线条相关的动画效果。
  - 有不少跟 **线条移动相关的动画**，就是使用这个属性来实现的。
- 方向
  - 正数：往左边偏移 <-
  - 负数：往右边偏移 ->

## 3. 💻 demos.1 - 使用 `ctx.lineDashOffset` 设置虚线的偏移量

::: code-group

<<< ./demos/1/1.html {16-44}

:::

- 最终效果：
  - ![img](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-10-03-23-07-43.png)
  - 一共 3 根线：
    - 第 1 根线作为参考
    - 第 2 根线向右偏移 50 个单位
    - 第 3 根线向左偏移 20 个单位
  - 越界自动截断
    - 这 3 根线绘制的横向（x 轴）有效区域是 [50, 450]，越界的部分将会自动截断隐藏。
