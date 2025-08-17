# [0023. 使用 ctx.beginPath 方法对路径进行分组](https://github.com/Tdahuyou/TNotes.canvas/tree/main/notes/0023.%20%E4%BD%BF%E7%94%A8%20ctx.beginPath%20%E6%96%B9%E6%B3%95%E5%AF%B9%E8%B7%AF%E5%BE%84%E8%BF%9B%E8%A1%8C%E5%88%86%E7%BB%84)

<!-- region:toc -->

- [1. 📝 概述](#1--概述)
- [2. 💻 demos.1 - `ctx.beginPath()` 的基本使用](#2--demos1---ctxbeginpath-的基本使用)

<!-- endregion:toc -->

## 1. 📝 概述

- 学会使用 `ctx.beginPath()` 对路径进行分组
- 了解如果不使用分组的话，会存在什么潜在问题

## 2. 💻 demos.1 - `ctx.beginPath()` 的基本使用

- **需求：**
  - 先在 `(50, 50)` 位置绘制一个 `100 x 100` 的矩形轮廓，要求轮廓颜色为蓝色；
  - 再在 `(250, 50)` 位置绘制一个 `100 x 100` 的红色矩形；
- 下面我们将通过上述这俩简单的小需求，体验一下 `ctx.beginPath()` 的作用。

::: code-group

<<< ./demos/1/1.html {17-34} [❌ 错误写法 - 未使用 ctx.beginPath() 对路径进行分组]

:::

- 最终效果：
  - ![img](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-10-04-00-52-36.png)
- stroke() 或 fill() 默认会对 **之前所有绘制的路径** 进行一个处理，这种写法在绘制完第一个描边矩形之后，当你绘制第二个填充矩形时，填充将会对之前的路径也起作用。
  - 当 `ctx.stroke()` 执行时
    - `(50, 50)` 位置的矩形：加上了蓝色的描边
  - 当 `ctx.fill()` 执行时
    - `(50, 50)` 位置的矩形：被填充为了红色
    - `(250, 50)` 位置的矩形：被填充为了红色

---

::: code-group

<<< ./demos/1/2.html {17-26} [✅ 正确写法 1 - 使用 ctx.beginPath() 对路径进行分组]

:::

- 最终效果：
  - ![img](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-10-04-00-53-46.png)
- 因为在执行 `ctx.fill()` 之前，调用了 `ctx.beginPath()`，相当于对路径做了一个分组，这意味着路径重新开始绘制，别再管之前的路径了。
  - 当 `ctx.stroke()` 执行时
    - `(50, 50)` 位置的矩形：加上了蓝色的描边
  - 当 `ctx.fill()` 执行时
    - ~~`(50, 50)` 位置的矩形：被填充为了红色~~（这是之前的路径，填充 fill 只会对当前的路径进行填充）
    - `(250, 50)` 位置的矩形：被填充为了红色

---

::: code-group

<<< ./demos/1/3.html {} [✅ 正确写法 2 - 使用 ctx.strokeRect()、ctx.fillRect()]

:::

- 最终效果：
  - ![img](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-10-04-00-54-27.png)
