# 実装計画

1. `pluginActions.installPluginFromGit` の例外処理を拡張し、短い要約メッセージと詳細エラー文字列を分離して返す。
2. `pluginManager.readManifest` で `plugin.json` 不在/不正を明示的なエラーコード付きで投げる。
3. `pluginSlice` で Git導入失敗時に `appendLog(detail)` を渡し、ログ明細に詳細を保存する。
4. `ActivityLogPanel` に「詳細を見る」導線を追加し、詳細はダイアログ表示にする。
5. ダイアログにコピー機能を実装し、`navigator.clipboard` 不可時はフォールバックコピーを使う。
6. スタイルを追加し、可読性と既存デザインの整合性を保つ。
7. `yarn typecheck` で検証する。
