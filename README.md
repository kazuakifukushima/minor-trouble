# minor-trouble（Quarto）

内科一般病棟の「マイナートラブル」対応を、**Quarto Website**として整理するプロジェクトです（研修医向け・教育用）。

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

1. リポジトリ **Settings → Pages** で、**Build and deployment** の Source を **`gh-pages` ブランチ**、フォルダ **`/ (root)`** に設定します。  
2. **`main` へ push** すると、`.github/workflows/publish.yml` が Quarto をレンダリングし、`gh-pages` へデプロイします。

## 文献の更新方針

- エントリは `references.bib` に集約します。  
- 章ごとに `@citekey` を本文へ入れると、章末の `::: {#refs} :::` にその章の参考文献が出ます。  
- ガイドラインは **版・更新日** を追えるように `@misc` の `note` や `url` を活用してください。

## ライセンス・免責

臨床内容は教育目的のたたき台です。個別診療の代替ではありません。公開範囲（GitHub Pages）に応じて、必要ならリポジトリ直下のライセンス方針（例: 文書は CC-BY、コードは MIT など）を別途定めてください。
