# Tech News

从 [JavaScript Weekly](https://javascriptweekly.com/) 和 [Frontend Focus](https://frontendfoc.us/) 抓取最新一期内容，生成 JSON 数据，并通过静态页面浏览与复制。

## 功能

- 抓取两封周刊的最新文章（标题、分类、摘要 HTML、链接、配图等）
- 输出 `dist/weeklyFeed.json`
- 静态页面双列展示文章，支持一键复制完整 JSON

## 快速开始

```bash
pnpm install
pnpm run dev
```

浏览器打开 http://localhost:3000 查看效果。

## 脚本

| 命令 | 说明 |
|------|------|
| `pnpm run build` | 抓取数据并构建 `dist/` |
| `pnpm run build:news` | 仅抓取并生成 `dist/weeklyFeed.json` |
| `pnpm run build:html` | 仅复制 `index.html` 到 `dist/` |
| `pnpm run dev` | 构建后启动本地预览 |
| `pnpm run serve` | 仅启动本地静态服务器（需已有 `dist/`） |

## 项目结构

```
tech.js        # 抓取入口
weekly.js      # 解析周刊 HTML，提取文章字段
index.html     # 静态阅读页
dist/          # 构建产物（GitHub Pages 部署目录）
```

## 部署

GitHub Actions 会在北京时间每周四、周五 18:00 自动构建，并将 `dist/` 部署到 GitHub Pages。推送至 `main` 分支也会触发构建。

## TODO

- [ ] GitHub Releases 追踪（如 [vite releases API](https://api.github.com/repos/vitejs/vite/releases)）
