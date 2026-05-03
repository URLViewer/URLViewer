# 修正内容の確認

## 変更点
- `src/web/store/pluginActions.ts`
  - Git導入エラーの分類を強化。
    - `plugin-manifest-not-found`
    - `plugin-manifest-invalid-json`
    - `plugin-manifest-invalid-schema`
    - `git-auth-failed`
    - `git-not-found-or-private`
    - `git-clone-failed`
    - `unknown`
  - 画面表示用の短いメッセージと、詳細ログ（name/message/stack）を分離。

- `src/electron/services/pluginManager.ts`
  - `readManifest` の失敗を明示的なエラーに変換。
    - `plugin-manifest-not-found`
    - `plugin-manifest-invalid-json`
    - `plugin-manifest-invalid-schema`

- `src/web/store/slices/pluginSlice.ts`
  - Git導入失敗時、`appendLog` に `detail` を保存するよう変更。

- `src/web/features/queue/ActivityLogPanel.tsx`
  - ログ行に「詳細を見る」ボタンを追加（`detail` があるときのみ）。
  - クリックで詳細ダイアログを開き、ログ全文を表示。
  - ダイアログにコピーボタンを追加。

- `src/web/styles/index.css`
  - 詳細ボタン、詳細ダイアログ、詳細テキスト表示用のスタイルを追加。

## 動作イメージ
- 通常表示: `導入失敗: plugin.json が見つかりません（tree URL でプラグインフォルダを指定してください）`
- 詳細表示: ログの「詳細を見る」からエラー詳細（stack 含む）を確認。
- コピー: ダイアログの「コピー」ボタンで詳細全文をクリップボードへコピー。

## 検証
- `yarn typecheck`（`UrlViewer-App`）成功。
