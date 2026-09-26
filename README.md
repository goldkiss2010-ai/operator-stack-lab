# Operator Stack Lab

画像処理を「パラメータの集まり」ではなく、**順番を持つ操作の列**として観察するためのブラウザ実験ツールです。

**Operator Stack Lab** treats image and signal processing as an ordered stack of operations. It visualizes pointwise transfer functions, lets you reorder operations, applies them to a local image, and extends the same stack to simple spatial/stochastic operators such as Gaussian Blur and Gaussian Noise.

## What it does

- 露出、明るさ、コントラスト、ガンマ、Log、Sカーブ、クリップなどを操作列として追加
- 操作順をドラッグ＆ドロップで変更
- pointwise 操作について、入力 `y = x` と合成された最終カーブ `F(x)` を表示
- `F'(x)` と `F''(x)` を解析表示
- ローカル画像に操作列をそのまま適用
- Gaussian Noise と Gaussian Blur を空間／確率的な操作として追加
- 1画素あたりの演算構成と、比較用の相対的な cost units を表示
- Big-O 記法も補助的に表示

## Try it

このリポジトリはビルド不要の静的HTMLです。

- `index.html` — 一般向けの説明ページ
- `lab.html` — Operator Stack Lab 本体

ローカルでは、ファイルを直接ブラウザで開くだけでも動作します。

GitHub Pages で公開する場合は、リポジトリのルートをそのまま公開してください。

## Concept

pointwise な操作だけなら、操作列

```text
x → f1 → f2 → … → fn
```

は最終的に一つの合成関数

```text
F = fn ∘ … ∘ f2 ∘ f1
```

として見ることができます。

一方、Gaussian Blur のような近傍画素に依存する処理を入れると、全体は単一の `F(x)` では表せません。Operator Stack Lab は、その境界も同じ操作列の中で観察できるようにしています。

## Image handling

読み込んだ画像はブラウザ内で処理されます。このツール自体は画像をサーバーへアップロードする処理を持ちません。

## Current scope and limitations

- pointwise 操作は RGB 各チャンネルのコード値に独立に適用します
- 現時点ではカラーマネジメントを行いません
- 表示時に出力を 0–1 にクリップします
- Gaussian Blur / Gaussian Noise を含む場合、カーブと微分は pointwise 部分のみを表示します
- cost units は操作列を比較するための相対値で、CPU/GPU上の実測時間ではありません
- Gaussian Blur のコスト表示は separable blur を前提とした概算です

## Repository structure

```text
operator-stack-lab/
├─ index.html
├─ lab.html
├─ README.md
├─ LICENSE
├─ CITATION.cff
├─ CHANGELOG.md
├─ CONTRIBUTING.md
├─ .gitignore
└─ .nojekyll
```

## Citation

学術・教育用途でこのツールが成果に寄与した場合は、`CITATION.cff` の情報を使って引用していただけると幸いです。GitHub は `CITATION.cff` を認識し、リポジトリ上に **Cite this repository** を表示できます。

## License

MIT License. See [`LICENSE`](LICENSE).

Copyright © 2026 Bungaku Yokota.
