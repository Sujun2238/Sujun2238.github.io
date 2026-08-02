---
title: "用 GitHub Actions 把 Astro 部署到 GitHub Pages"
pubDate: 2026-08-02
description: "记录从零搭建 Astro 并自动部署到 GitHub Pages 的关键步骤。"
---

本文记录把 Astro 站点通过 GitHub Actions 自动部署到 GitHub Pages 的关键配置。

## 1. 配置 site

在 `astro.config.mjs` 中设置站点地址。如果仓库名为 `用户名.github.io`，则无需 `base`：

```js
import { defineConfig } from 'astro/config';

export default defineConfig({
  site: 'https://Sujun2238.github.io',
});
```

> 如果仓库名不是 `用户名.github.io`，需要补上 `base: '/仓库名'`。

## 2. 部署工作流

在 `.github/workflows/deploy.yml` 中添加：

```yaml
on:
  push:
    branches: [main]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write
```

关键点：

- `pages: write` 和 `id-token: write` 是部署 Pages 必需的权限
- 监听 `main` 分支，与本地主分支名保持一致

## 3. 启用 Pages

推送完成后，在仓库 **Settings → Pages → Source** 中选择 **GitHub Actions**，保存即可。

## 4. 注意事项

- `package-lock.json` 必须提交，Astro Action 靠它识别包管理器
- 首次部署若失败，多半是忘记在 Pages 设置里选 Source，设置后重跑 workflow 即可

就这样，每次 `git push` 都会自动发布，省心！
