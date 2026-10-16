# takasetaigat1.github.io

個人研究 HP のソース。Jekyll（GitHub Pages 標準）で動きます。
HTML を触らずに、`_config.yml` と `_data/` の YAML を書き換えるだけで内容を更新できます。

## 更新のしかた（基本）

GitHub のリポジトリ画面でファイルを開き、鉛筆アイコン → 編集 → 「Commit changes」。
数十秒〜数分でサイトに反映されます（Actions タブで進捗が見られます）。

| 変えたいもの | 触るファイル |
|---|---|
| 氏名・所属・メール・外部リンク・ナビ | `_config.yml` |
| ニュースを足す | `_data/news.yml`（一番上に追記） |
| 論文を足す | `_data/publications.yml`（一番上に追記） |
| 学会発表を足す | `_data/presentations.yml`（一番上に追記） |
| 研究テーマの文章・図 | `_data/topics.yml`、図は `assets/img/research/` に置く |
| 経歴・受賞・研究費・活動 | `_data/profile.yml` |
| トップページの自己紹介文 | `index.html` の `<p class="lead">` の中 |
| 英語ページ | `en/index.html` |
| 顔写真 | `assets/img/profile.jpg` を差し替え（縦長推奨） |
| 色・フォント | `assets/css/style.css` の冒頭 `:root` |

### ニュースの例

```yaml
- date: 2026-11-05
  text: 日本惑星科学会 2026 年秋季講演会にて口頭発表を行いました
  tag: 発表
```

### 論文の例

```yaml
- category: first_published      # first_published / first_submitted / coauthor
  year: 2026
  authors: "<me>T. Takase</me>, T. Nakamura, and M. Matsumoto"
  title: "Micro-FTIR comparison of Ryugu and Bennu samples"
  journal: "Icarus"
  volume: "420"
  pages: "116xxx"
  doi: "10.1016/j.icarus.2026.116xxx"
```

`<me>…</me>` で囲んだ名前は太字で表示されます。

## 公開の手順（最初の 1 回だけ）

1. リポジトリの **Settings → Pages**
2. **Source** を「Deploy from a branch」、**Branch** を `main` / `/ (root)` にして **Save**
3. 数分後に https://takasetaigat1.github.io で公開

公開前にプレビューしたい場合は、Settings → Pages を設定したうえで、
ビルドされた URL を自分だけで確認し、納得してから他の人に知らせる、という運用でも十分です。

## ローカルで確認したい場合（任意）

Ruby と Bundler が入っていれば：

```
bundle install
bundle exec jekyll serve
```

で http://localhost:4000 に表示されます。
