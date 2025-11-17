---
author: Sat Naing
pubDatetime: 2022-09-23T15:22:00Z
modDatetime: 2025-06-13T16:52:45.934Z
title: Flex
slug: flex
featured: true
draft: false
tags:
  - docs
description: Flex
---

## 🎯 Flex 中到底有哪些“轴”和“对象”？

**Flex 的所有属性都是围绕两个维度：**

### 1）轴线（重要！）

* **主轴 main axis**：由 `flex-direction` 决定（默认横向 →）
* **交叉轴 cross axis**：垂直于主轴

### 2）对象

* **Container（容器）**：父元素
* **Items（项目）**：子元素

所有属性就是围绕这 4 个东西组合出的。

---

# 🧩 一图记住 Flex 的分类（最重要）

```
           主轴(main axis)            交叉轴(cross axis)
容器层面   justify-content             align-content
项目层面   ?? (没有主轴上的)            align-items / align-self
```

### 🔸 容器层（作用于整行/整列）

* `justify-content` —— 控制 **主轴上** 如何分布
* `align-content` —— 控制 **交叉轴上多行/多列** 的整体分布（要多行才生效）

### 🔸 项目层（作用于单个 item 或全体 item）

* `align-items` —— 控制 **所有项目** 在交叉轴上的对齐
* `align-self` —— 控制 **单个项目** 在交叉轴上的对齐

---

# 🌟 完整解释（带你彻底掌握）

---

## ① justify-content（容器、主轴）

**决定项目如何在主轴上分布。**

主轴如果是横向，就是水平对齐；
主轴如果是纵向，就是垂直分布。

常见值：

* `flex-start`
* `center`
* `flex-end`
* `space-between`
* `space-around`
* `space-evenly`

例子：

```css
justify-content: center;
```

所有子元素在主轴上居中。

---

## ② align-items（容器、交叉轴）

**控制所有子元素在交叉轴上的对齐方式（单行时用它）**

常见值：

* `flex-start`
* `center`
* `flex-end`
* `baseline`
* `stretch`（默认）

例子：

```css
align-items: center;
```

所有子元素在交叉轴方向居中。

---

## ③ align-self（项目、交叉轴）

**单个 item 的 align-items 覆盖版**

例子：

```css
.item1 {
  align-self: flex-end;
}
```

只让第一个元素在交叉轴底部对齐。

---

## ④ align-content（容器、多行、交叉轴）

**当 flex-wrap: wrap 时，控制“多行之间”怎么分布**

⚠️ 很多人误用，因为它：

* 只有 **多行** 才生效
* 控制的是“行之间”的间距，而不是单个元素

常见值：

* `flex-start`
* `center`
* `flex-end`
* `space-between`
* `space-around`
* `stretch`

例子：

```css
flex-wrap: wrap;
align-content: space-between;
```

多行之间平均分布。

---

# 🔥 核心口诀（记住就通了）

### **1. 主轴：justify-content 分布**

### **2. 交叉轴：align-items 单行对齐**

### **3. 多行时：align-content 行之间对齐**

### **4. 单个元素：align-self**

**一句话：
“主轴 justify，交叉轴 align。单个 self，多行 content。”**

---

# 🌈 总结表（最清晰版）

| 属性              | 作用对象 | 作用轴 | 作用场景             |
| --------------- | ---- | --- | ---------------- |
| justify-content | 容器   | 主轴  | 项目的主轴位置关系        |
| align-items     | 容器   | 交叉轴 | 单行项目的交叉轴对齐       |
| align-self      | 单个项目 | 交叉轴 | 覆盖 align-items   |
| align-content   | 容器   | 交叉轴 | 多行之间的分布（需要 wrap） |

---

如果你愿意，我可以给你：

* 一张更直观的图（图解主轴/交叉轴）
* 一个交互式在线 Demo
* 或者你贴一个实际布局，我帮你选哪几个属性最合适。
