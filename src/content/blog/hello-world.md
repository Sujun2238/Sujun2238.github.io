---
title: "你好，世界"
pubDate: 2026-08-02
description: "博客的第一篇文章，介绍这个站点的由来与技术栈。"
---

欢迎来到我的博客！这是第一篇文章。

## 为什么写博客

这是一个用来记录学习与思考的地方。把学到的东西写下来，既是对自己的梳理，也希望能帮到路过这里的你。

## 技术栈

这个站点由 [Astro](https://astro.build/) 构建，通过 GitHub Actions 自动部署到 GitHub Pages。

- **框架**：Astro（静态站点生成器，默认零 JS，性能出色）
- **内容**：Markdown 文件 + Astro 内容集合（Content Collections）
- **部署**：推送到 `main` 分支后，GitHub Actions 自动构建并发布

下面是一段示例代码：

```js
function greet(name) {
  return `Hello, ${name}!`;
}

console.log(greet('博客'));
```

## 接下来

我会陆续更新一些技术笔记和生活随笔。感谢你的访问！
