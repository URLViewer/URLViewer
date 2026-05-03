# 修正内容の確認

## 変更点
- `src/web/features/library/LibraryPanel.tsx`
  - ヘッダーを2段化。
    - 1段目: `ライブラリ` + 件数 + `選択`
    - 2段目: 並び替えチップ + 昇降順ボタン
  - タイトルに `whitespace-nowrap` を付与。
  - 動画アクションボタンに `video-action-btn` クラスを付与し、サイズを統一縮小。

- `src/web/styles/index.css`
  - `.library-sort-chip` に `whitespace-nowrap` を追加。
  - `.video-item-actions` の最小幅依存を廃止し `shrink-0` + `gap-1` へ変更。
  - `.video-action-btn` を追加（`h-8 w-8`）。

## 期待される改善
- `ライブラリ` タイトルや `追加順` が縦積みにならない。
- 動画名入力欄の幅が広がり、拡張子手前で過剰に切れない。

## 検証
- `yarn typecheck`（`UrlViewer-App`）成功。
