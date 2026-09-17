# pikaray168.github.io

個人部落格，記錄日常、技術文章與作品。

- 網址：<https://pikaray168.github.io>
- 主題：[Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy)（以 gem 方式引入）
- 部署：push 到 `main` 後由 GitHub Actions 自動建置並發布到 GitHub Pages

## 發一篇新文章

1. 在 `_posts/` 新增檔案，檔名為 `YYYY-MM-DD-英文-slug.md`（**檔名用英文**，標題才用中文）
2. 複製 `_posts/2026-09-17-tech-post-template.md` 的 front matter 來改
3. 分類固定用這三類（第二層可自由命名）：
   - `categories: [日常]`
   - `categories: [技術, 子分類]`
   - `categories: [作品]`
4. 圖片放 `assets/img/posts/`，用 `/assets/img/posts/xxx.png` 引用
5. `git add -A && git commit -m "post: 標題" && git push`
6. 等 Actions 跑完（約 1–2 分鐘）就上線了

> 圖片或內部連結指向不存在的檔案時，Actions 的 htmlproofer 檢查會讓建置失敗。

## 常見設定位置

| 想改什麼 | 改哪裡 |
| --- | --- |
| 站名、副標、簡介、頭像 | `_config.yml` |
| 側欄社群圖示 | `_data/contact.yml` |
| 關於我 | `_tabs/about.md` |
| 作品列表 | `_tabs/projects.md` |
| 留言、分析工具 | `_config.yml` 的 `comments` / `analytics` |

## 升級主題

改 `Gemfile` 裡 `jekyll-theme-chirpy` 的版本號後 push 即可。

## 本機預覽（選配，目前未安裝）

需要 Ruby 環境。安裝 [RubyInstaller with Devkit](https://rubyinstaller.org/) 後：

```bash
bundle install
bundle exec jekyll serve
```

也可以用 repo 內附的 `.devcontainer/`（需要 Docker Desktop + VS Code Dev Containers）。
