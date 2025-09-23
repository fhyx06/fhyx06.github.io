---
title: Hexo
date: 2025-09-22 16:27:04
tags:
---

1. **在本地搭建 Hexo：**

- 确保本地安装了 Node.js 和 Git。

- ``````bash
  node -v  # 查看node版本
  npm -v  # 查看包管理工具版本
  ``````

- 运行 `npm install -g hexo-cli` 安装 Hexo。

- 在一个空文件夹里运行 `hexo init my-blog` 来初始化一个 Hexo 项目。

- `cd my-blog` 然后 `npm install`。

- 运行 `hexo server`，在浏览器访问 `http://localhost:4000` 看到默认博客页面。

2. **创建 GitHub 仓库：**

- 在 GitHub 上创建一个新的公开仓库（Public），例如名为 `my-blog`。

- 将本地的 Hexo 项目初始化为一个 Git 仓库，并关联到这个远程仓库。

- ```bash
  git init   # 初始化
  git add .
  git commit -m "initial commit"
  git branch -M main
  git branch
  git remote add origin https://github.com/用户名/仓库名.git
  git pull origin main  # 拉取远程仓库的更新并合并到本地
  git push -u origin main
  
  # 后续更新推送
  hexo g   # 生成静态文件
  git add .
  git commit -m "提交提示"
  git push
  ```
  
  