# 李醫師的鳩是魔法 · DrLeeDoveMagic

白斑鳩的日常飼育、育雛、訓練與鴿子魔術紀錄。

**網站網址：https://drleedovemagic.net**
（網域在 Cloudflare 註冊與管理，DNS 指向 GitHub Pages）

以 Jekyll 建置，由 GitHub Pages 自動發佈——**你不需要在電腦上安裝任何東西**，
把 Markdown 檔案推上 GitHub 就會自動變成網頁。

---

## 怎麼寫一篇新文章

在 `_posts/` 資料夾新增一個檔案，檔名格式固定為 `年-月-日-英文代號.md`：

```
_posts/2026-10-05-first-flight.md
```

> 檔名裡的英文代號會變成網址的一部分，所以請用英文或數字，不要用中文。
> 標題用中文寫在檔案裡面就好。

檔案內容長這樣，最上面用三個減號框起來的部分叫 front matter，是文章的基本資料：

```markdown
---
title: 第一次放飛
categories: [training]
description: 一句話說明這篇在寫什麼，會顯示在首頁的卡片上。
---

這裡開始寫正文。空一行就是分段。

## 這是小標題

**粗體**、*斜體*、[連結](https://example.com) 都可以直接用。

- 項目一
- 項目二

![照片說明](/assets/img/你的照片.jpg)
```

`categories` 只能填下面六個代號之一：

| 代號 | 分類 | 內容 |
|---|---|---|
| `daily` | 鳩日常 | 餵食、換水、放飛與相處 |
| `hatchling` | 鳩來了 | 配對、孵蛋、育雛、離巢 |
| `training` | 鳩上手 | 從親人到能配合演出 |
| `health` | 鳩診室 | 健康觀察、換羽、照護 |
| `knowledge` | 鳩知道 | 品種、習性、飼養知識 |
| `magic` | 鳩是魔法 | 手法、道具、表演紀錄 |

## 放照片

把圖片放進 `assets/img/`，在文章裡用 `![說明](/assets/img/檔名.jpg)` 引用。

## 要改分類、站名、簡介的時候

| 想改什麼 | 改哪個檔案 |
|---|---|
| 站名、副標、網站簡介 | `_config.yml` |
| 六個分類的名稱與說明 | `_data/categories.yml` |
| 首頁的文案與區塊 | `index.html` |
| 關於我 | `about.md` |
| 顏色、字體、版面 | `assets/css/style.css` |

新增分類要做兩件事：在 `_data/categories.yml` 加一段，並在 `categories/` 底下
複製一個現有資料夾、把裡面的 `slug` 改成新代號。

## 網站結構

```
├── index.html              首頁
├── about.md                關於李醫師
├── archive.html            全部文章
├── categories/             六個分類頁
├── _posts/                 所有文章寫在這裡
├── _data/categories.yml    分類設定
├── _layouts/               頁面骨架
├── _includes/              共用零件（頁首、頁尾、卡片）
└── assets/css/style.css    樣式
```

## 本機預覽（選用，需要先安裝 Ruby）

```bash
bundle install
bundle exec jekyll serve
```

然後打開 http://localhost:4000

不想安裝也完全沒問題——直接推上 GitHub，等一兩分鐘就能在線上看到結果。

## 換掉首頁主視覺

首頁那張舞台照放在 `assets/img/`，共三個檔案：

| 檔案 | 用途 |
|---|---|
| `hero.jpg` | 電腦版顯示（1800px 寬） |
| `hero-960.jpg` | 手機版顯示（960px 寬） |
| `hero-original.jpg` | 原始檔備份，網站不會用到 |

要換照片的話，把新照片做成同樣的兩個尺寸、用同樣的檔名蓋掉就好，
版型不用動。**照片請盡量選背景深色的**——首屏的底色是近黑色，深色背景
才會融進版面看不出邊界。順帶一提，這張照片同時也是分享連結到 LINE、
Facebook 時顯示的預覽圖。

## 網站圖示（favicon）

瀏覽器分頁、手機書籤用的圖示，來源是白斑鳩與聽診器的站徽：

| 檔案 | 用途 |
|---|---|
| `favicon.ico` | 瀏覽器分頁（內含 16／32／48 三種尺寸） |
| `assets/img/favicon-32.png`、`favicon-16.png` | 現代瀏覽器分頁 |
| `assets/img/apple-touch-icon.png` | iPhone／iPad 加到主畫面時的圖示 |
| `assets/img/icon-512.png` | 大尺寸備用 |
| `assets/img/logo.png` | 原本的淺紫底版本，給網頁內容使用 |

圖示用的是深紫底白鴿——原圖的淺紫底白鴿縮到 16px 幾乎看不見，
深底才有足夠對比。要換圖示的話，把這幾個檔案照同樣尺寸重做即可。

## 文章範本

`_drafts/文章範本.md` 是一份空白範本，裡面寫了完整的填寫說明。
放在 `_drafts/` 的檔案**不會出現在網站上**，可以安心留著當參考。

要寫新文章時，把它複製到 `_posts/`、改成 `年-月-日-英文代號.md` 的檔名即可。
