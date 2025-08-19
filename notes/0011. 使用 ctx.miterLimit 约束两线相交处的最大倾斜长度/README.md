# [0011. 使用 ctx.miterLimit 约束两线相交处的最大倾斜长度](https://github.com/Tdahuyou/TNotes.canvas/tree/main/notes/0011.%20%E4%BD%BF%E7%94%A8%20ctx.miterLimit%20%E7%BA%A6%E6%9D%9F%E4%B8%A4%E7%BA%BF%E7%9B%B8%E4%BA%A4%E5%A4%84%E7%9A%84%E6%9C%80%E5%A4%A7%E5%80%BE%E6%96%9C%E9%95%BF%E5%BA%A6)

<!-- region:toc -->

- [1. 📝 概述](#1--概述)
- [2. 📒 `miterLimit`](#2--miterlimit)
- [3. 💻 demos.1 - `miterLimit` 的基本使用](#3--demos1---miterlimit-的基本使用)
- [4. 🔗 References](#4--references)

<!-- endregion:toc -->

## 1. 📝 概述

- `miterLimit` 的基本使用

## 2. 📒 `miterLimit`

- `miterLimit` 控制的是角从 `miter` 类型变为 `bevel` 类型的阈值。
- 本节介绍的内容，和下面这个公式有关。

$$
\text{miterLimit} = \frac{\text{miterLength（斜接长度）}}{\text{lineWidth（线条宽度）}}
$$

- 通过下面这张图，认识 `lineWidth`、`miterLength` 表示的分别是哪部分的尺寸。
  - ![img](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-10-03-23-11-03.png)
- 通过下面这张图，认识什么是 `round`、`miter`、`bevel`
  - ![图 0](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2025-08-18-20-14-47.png)
- `ctx.miterLimit`
  - `ctx.miterLimit` 是 HTML5 Canvas 2D API 中的一个属性，用于设置或返回当两条线相交时接合处的最大斜接长度（miter length）。
  - 斜接长度是指在两条线相交形成尖角时，内角顶点到外角顶点的距离。
  - 这个属性主要用于控制具有 miter 接合类型的线条边角的外观。
- 越大越尖、越小越平
  - `miterLimit` 值是一个大于等于 `1` 的数字，它表示允许的最大斜接长度与线条宽度的比率，默认值通常是 `10`。
  - 如果斜接长度超过 `miterLimit` 的值，边角会以 `lineJoin` 的 `]` 类型来显示。
  - 当 `miterLimit` 设置得较小，如接近于 `1` 时，只要相交角稍微尖锐一点，接合方式就会从 `miter` 转为 `bevel`。
  - 当 `miterLimit` 设置得较大时，即使是非常尖锐的角，接合处也会尝试保持 `miter` 类型，可能导致角部分非常尖长。
- 应用场景
  - 如果角度非常尖锐，斜接长度可能会异常长，导致图形显示不理想。
  - 比如，当线条比较粗，折线夹角比较小的时候，`lineJoin` 的 `miter` 设置形成的尖就会很长，这时候可以利用该属性来控制尖角的长短。
  - `miterLimit` 属性允许你设置一个阈值，超过这个值的斜接长度会自动转换为 bevel 类型的接合，即切去尖角部分。
- 小结
  - 角可以尖、可以长，但是得有个度，这个度就是 `miterLimit`。
  - 换算公式： $miterLimit = miterLength / lineWidth$

## 3. 💻 demos.1 - `miterLimit` 的基本使用

::: code-group

<<< ./demos/1/1.html {20-58}

<<< ./demos/1/2.html {20-43}

:::

- `1.html`
  - ![img](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-10-03-23-11-26.png)
- `2.html`
  - ![img](https://cdn.jsdelivr.net/gh/Tdahuyou/imgs@main/2024-10-03-23-11-54.png)

## 4. 🔗 References

- https://developer.mozilla.org/zh-CN/docs/Web/API/CanvasRenderingContext2D/miterLimit
  - MDN doc: `miterLimit`
