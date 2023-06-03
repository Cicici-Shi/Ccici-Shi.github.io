---
title: "基于JSON Schema的表单生成器"
subtitle: "一种快速、灵活、可扩展的表单开发方案"
description: ""
date: 2023-04-04
author: 施艳春
image: ""
tags: ["fe", "note"]
categories: ["Tech"]
---

演示地址：[https://vue3-json-schema-form.vercel.app/](https://vue3-json-schema-form.vercel.app/)

# 什么是 JSON Schema

JSON Schema 是一种用于描述和验证 JSON 数据结构的规范。它可以用来定义数据的类型、格式、约束等属性，以及为数据提供文档和注释。

## 特点：

- JSON Schema 本身也是一个 JSON 对象，可以使用相同的语法和工具来处理。
- JSON Schema 支持多种编程语言和平台，可以跨系统交互。
- JSON Schema 支持自定义关键字和扩展，可以适应不同的需求。

## JSON Schema 生成表单的优点

### 简化开发流程

只需要编写一个 Schema 即可生成一个表单。我们不需要再花时间去编写 HTML、CSS、JavaScript 等代码来创建界面元素。我们也不需要再担心代码出错或难以维护。

### 提高开发效率

我们可以快速修改和更新 Schema 和表单。 如果我们想要改变数据结构或规则，我们只需要修改 Schema 即可，不需要再修改表单界面。这样，我们就可以节省很多时间和精力。

### 保证数据质量

我们可以利用 Schema 进行数据验证和提示。当用户输入或查看数据时， 我们可以根据 Schema 来检查数据是否符合我们的要求和格式，并且给出相应的错误提示或修正建议。 这样，我们就可以避免数据出现错误、缺失、冲突、攻击等问题。

# 如何使用 JSON Schema 生成表单

## 登录表单示例

![](/img/2023-04-04-vue3-json-schema-form/register.png)

#### Object

包裹多个 schema，将转换为各种不同类型的 schemaItem

#### Array

- 单类型数组 single-type { items: { type: string } }
- 固定长度，多类型数组 fixed length & multi-type { items: [ { type: string }, { type: number } ] }
- 多选类型数组 multi-select { items: { type: string, enum: ['1', '2']} }
- 多文件上传 { upload: true }

#### String

普通输入框
文本区域 { rows: '4', }
选择颜色 { format: 'color', }
单文件上传 { upload: true }
日期选择 { date: true }
邮箱 { email: true }
网址 { url: true }

#### Number

仅输入数字的输入框，带有步进箭头 单项下拉框 单选按钮

# 实现原理

![](/img/2023-04-04-vue3-json-schema-form/realization.png)

# 总结和展望

基于 JSON Schema 的表单生成器是一种快速、灵活、可扩展的表单开发方案，它可以帮助我们提高开发效率、保证数据质量、增强用户体验。

### Todo：

- 引入 vuedraggable 插件，实现组件拖拽，更像低代码平台。
- 引入 elementplus、Iview 等组件库，使表单更美观。
- 提升单测覆盖率
