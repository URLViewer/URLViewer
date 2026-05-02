# 実装計画

## 方針
1. `installFromGit` の制約（`plugin.json` ルート直下必須）を最優先で満たす。
2. 実用性のある `input-panel` プラグインを1本追加する。
3. テスト導入しやすいように build 済み `dist/index.js` を同梱する。

## 実装手順
1. `UrlViewer-Plugins/plugin.json` を新規作成。
2. `UrlViewer-Plugins/dist/index.js` にランタイム実装を追加。
3. `UrlViewer-Plugins/src/index.ts` にソース実装を追加。
4. `.gitignore` で `dist/index.js` を追跡対象へ変更。
5. `README.md` に公開プラグイン情報を追記。
6. Node 実行で `resolveToVideoSources` の動作を簡易検証。
