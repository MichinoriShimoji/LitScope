# LitSearch

ブラウザだけで動く文献収集ツールと、収集済みの文献リスト（伊良部島方言ほか）。

## ツール（GitHub Pages）

🔗 **https://michinorishimoji.github.io/LitSearch/**

サーバー不要、データはローカル（ブラウザの localStorage）に留まり、成果物は ZIP で一括ダウンロードできます。

3段階のワークフロー：

1. **Stage 1 — キーワード検索**：Crossref + OpenAlex を並列検索 → 候補を編集 → 本体CSVへ追加
2. **Stage 2 — 孫引き一括抽出**：本体CSV内のDOI付きレコードから参考文献を Crossref で再取得し、自動再検証。失敗したものは「未検証フラグ」付きで本体に出る
3. **Stage 3 — 確認・ダウンロード**：未検証カードを編集/削除 → ZIP（CSV / BibTeX / Zotero用 BibTeX / PDF URLリスト / 未検証CSV）

詳しい使い方は [docs/README.md](docs/README.md) を参照。

## 含まれる文献リスト

| ファイル | 内容 |
|---|---|
| `irabu_dialect_literature.csv` / `.bib` | 伊良部島方言の文献リスト |
| `zotero_import_irabu_tagged.bib` | Zotero取り込み用（tag付き） |
| `irabu_derivative_candidate_verification.csv` | 未確認候補 |
| `shiiba_*.csv` / `.bib` | 椎葉方言（初期段階） |

PDFs は著作権の都合で除外しています（`.gitignore`）。

## ライセンス

ツール部分（`docs/index.html`）は MIT。文献リストデータは公開済みメタデータ由来。
