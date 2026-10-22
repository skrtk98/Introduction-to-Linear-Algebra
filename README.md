# 線形代数学入門

線形代数学の原稿を管理する。本文は `manuscripts/index.md` に置く。

公開先：<https://skrtk98.github.io/Introduction-to-Linear-Algebra/>

## 使い方

Node.js 20 以上と、TikZ の変換に使う `latex` と `dvisvgm` を用意して、依存関係をインストールする。

```bash
npm ci
```

- `npm run preview`：`http://localhost:4173/` でプレビューを開く。原稿を保存すると自動で再読み込みする。
- `npm run check`：公開対象の原稿を変換できることを確認する。
- `npm run build`：公開用 HTML を `site/` に生成する。

`main` に push すると、GitHub Actions が `site/` を生成して GitHub Pages に公開する。
`site/` はコミットしない。

変換とプレビューには [math-notes-previewer](https://github.com/skrtk98/math-notes-previewer) を使う。
ほかの原稿は <https://skrtk98.github.io/> から一覧できる。
