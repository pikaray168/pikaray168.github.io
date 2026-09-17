---
title: 技術文章範本：Chirpy 排版語法速查
date: 2026-09-17 11:00:00 +0800
categories: [技術, 寫作]
tags: [chirpy, jekyll, markdown]
description: 這篇同時是一篇範例，也是我自己的語法速查表。寫新的技術文章時直接複製這個檔案來改。
math: true
mermaid: true
---

寫技術文章時常用到的 Chirpy / Markdown 語法都放在這裡，要用的時候回來複製。

## Front matter

每篇文章開頭的設定區塊：

```yaml
---
title: 文章標題
date: 2026-09-17 11:00:00 +0800   # 記得帶 +0800 時區
categories: [技術, 寫作]          # 最多兩層：[主分類, 子分類]
tags: [chirpy, jekyll]            # 標籤數量不限，建議用小寫
description: 一句話摘要，會顯示在列表與 SEO meta。
math: true                        # 需要數學式才開
mermaid: true                     # 需要流程圖才開
pin: true                         # 置頂
image:                            # 封面圖（檔案要真的存在，否則建置會失敗）
  path: /assets/img/posts/cover.png
  alt: 圖片替代文字
---
```

## 程式碼

行內程式碼用 `backtick` 包起來。區塊要標語言才有語法高亮：

```python
def fib(n: int) -> int:
    a, b = 0, 1
    for _ in range(n):
        a, b = b, a + b
    return a
```

指定檔名的話，在程式碼區塊後面加一行：

```bash
git add -A && git commit -m "new post" && git push
```
{: file="發布流程" }

## 提示框

Chirpy 提供四種顏色的提示框，寫法是在引言後面加一個 class：

> 補充說明用這個。
{: .prompt-info }

> 小技巧用這個。
{: .prompt-tip }

> 需要注意的地方用這個。
{: .prompt-warning }

> 會出事的地方用這個。
{: .prompt-danger }

## 圖片

圖片放在 `assets/img/posts/` 底下，語法如下（**檔案必須存在**，否則 GitHub Actions 的 htmlproofer 檢查會讓建置失敗）：

```markdown
![替代文字](/assets/img/posts/example.png)
_圖片說明文字_

<!-- 指定寬高，避免載入時版面跳動 -->
![替代文字](/assets/img/posts/example.png){: width="700" height="400" }

<!-- 靠左 / 靠右 / 置中 -->
![替代文字](/assets/img/posts/example.png){: .left }
```

## 數學式

開啟 `math: true` 之後，行內用 `$$ ... $$`：時間複雜度是 $$O(n \log n)$$。

獨立一行：

$$
\sum_{i=1}^{n} i = \frac{n(n+1)}{2}
$$

## 流程圖

開啟 `mermaid: true` 之後：

```mermaid
graph LR
  A[寫 Markdown] --> B[git push]
  B --> C[GitHub Actions 建置]
  C --> D[GitHub Pages 上線]
```

## 檔名與路徑

檔案路徑用這個標記會有特別樣式：`_posts/2026-09-17-example.md`{: .filepath }

## 命名規則

- 檔名：`YYYY-MM-DD-英文-slug.md`，**用英文 slug**。中文檔名會讓網址變成一長串編碼，不好分享也不利搜尋。
- 標題：中文照寫，網址不受影響。

## 草稿

還沒寫完的放 `_drafts/`{: .filepath }（不用日期前綴），不會被發布，本機預覽時加 `--drafts` 才看得到。
