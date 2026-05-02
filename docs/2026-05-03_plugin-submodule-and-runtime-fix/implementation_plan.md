# 実装計画

## 方針
1. プラグイン管理構成の修正（`UrlViewer-Plugins` 側）と、実行経路の修正（`UrlViewer-App` 側）を分離して実施する。
2. App 側は `pluginManager` を中心に、外部 plugin の panel 解決と input 実行を main process で完結させる。
3. 既存エラーハンドリング（`plugin-timeout`, `plugin-entry-load-failed`, `plugin-runtime-error`）を維持する。

## 実装手順
1. `UrlViewer-Plugins` の plugin ファイルを `url-extractor-input-plugin/` へ移設。
2. `README.md` / `.gitmodules` / plugin README を更新。
3. `UrlViewer-App/src/shared/schemas.ts` に `pluginResolveInputSchema` を追加。
4. `pluginManager` に次を追加。
   - 外部 plugin entry の安全解決
   - dynamic import + runtime.input 取得
   - `getInputPanels` の runtime 反映
   - `resolveInput(pluginId, input, timeoutMs)` 実行
5. `ipc/preload/vite-env` に `plugins:resolveInput` を配線。
6. Renderer store を `plugins.resolveInput` / `plugins.listPanels` 起点へ変更。
7. `yarn typecheck` 実行。
