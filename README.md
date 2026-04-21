# minor-trouble（Quarto）

内科一般病棟の「マイナートラブル」対応を、**Quarto Website**として整理するプロジェクトです（**初期研修医向け**・教育用）。

構成は Obsidian の構成案に沿い、**①総論 → ⑦付録** のパート別サイドバーに整理しています。新規ページは `topics/TEMPLATE-topic.txt` を `.qmd` にコピーして作成します。

ローカル開発フォルダ名は `quarto-minor-trouble` でも構いません。GitHub 上のリポジトリは **[kazuakifukushima/minor-trouble](https://github.com/kazuakifukushima/minor-trouble)** です。

## 前提

- [Quarto](https://quarto.org/)（推奨: 最新の1.4+）
- ローカルプレビューに R は必須ではありません（図は主に Mermaid）。

## ローカル

このディレクトリ（リポジトリルートに `_quarto.yml` がある状態）で:

```bash
quarto preview
```

HTML のみ生成:

```bash
quarto render
```

成果物は `_site/` に出力されます。

## GitHub Pages

公開 URL: **`https://kazuakifukushima.github.io/minor-trouble/`**（Pages 設定後）

1. リポジトリ **Settings → Actions → General → Workflow permissions** で **Read and write permissions** を有効にします（`gh-pages` への push に必要）。  
2. **Settings → Pages** で、**Build and deployment** の Source を **`gh-pages` ブランチ**、フォルダ **`/ (root)`** に設定します。  
3. **`main` へ push**（または Actions の **Publish Quarto site** を手動実行）すると、`quarto render` した `_site/` を **`peaceiris/actions-gh-pages`** で `gh-pages` ブランチへ載せ替えます（初回から `gh-pages` が無くても作成されます）。

## 文献の更新方針

- エントリは `references.bib` に集約します。  
- 章ごとに `@citekey` を本文へ入れると、章末の `::: {#refs} :::` にその章の参考文献が出ます。  
- ガイドラインは **版・更新日** を追えるように `@misc` の `note` や `url` を活用してください。

## ライセンス・免責

臨床内容は教育目的のたたき台です。個別診療の代替ではありません。公開範囲（GitHub Pages）に応じて、必要ならリポジトリ直下のライセンス方針（例: 文書は CC-BY、コードは MIT など）を別途定めてください。
