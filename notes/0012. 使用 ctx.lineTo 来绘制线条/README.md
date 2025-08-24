# [0012. 使用 ctx.lineTo 来绘制线条](https://github.com/Tdahuyou/TNotes.canvas/tree/main/notes/0012.%20%E4%BD%BF%E7%94%A8%20ctx.lineTo%20%E6%9D%A5%E7%BB%98%E5%88%B6%E7%BA%BF%E6%9D%A1)

<!-- region:toc -->

- [1. 🎯 目标](#1--目标)
- [2. 🫧 评价](#2--评价)
- [3. 💻 demos.1 - 绘制线条](#3--demos1---绘制线条)

<!-- endregion:toc -->

## 1. 🎯 目标

- 掌握 `ctx.lineTo` 的基本使用

## 2. 🫧 评价

- lineTo 绘制的线段是连续的值的线段，如果要打断，重新开始新的线段，需要使用 `ctx.beginPath()` 方法来开始新的路径。

## 3. 💻 demos.1 - 绘制线条

::: code-group

<<< ./demos/1/1.html {17-27}

<<< ./demos/1/2.html {17-25}

:::

::: swiper

![1](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-10-03-23-13-29.png)

![2](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-10-03-23-13-41.png)

:::

- `1.html` - 如果 `lineWidth` 比较大，绘制出来的效果就好比一个填充矩形
- `2.html` - 不断地调用 `lineTo` 会将线条连在一起
