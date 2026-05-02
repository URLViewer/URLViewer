# 修正内容の確認

## 1. `UrlViewer-Plugins` 側

### 変更ファイル
- `UrlViewer-Plugins/README.md`
- `UrlViewer-Plugins/.gitignore`
- `UrlViewer-Plugins/.gitmodules`（新規）
- `UrlViewer-Plugins/url-extractor-input-plugin/README.md`（新規）
- `UrlViewer-Plugins/url-extractor-input-plugin/plugin.json`
- `UrlViewer-Plugins/url-extractor-input-plugin/dist/index.js`
- `UrlViewer-Plugins/url-extractor-input-plugin/src/index.ts`

### 内容
- ルート直下 plugin 配置を廃止し、`url-extractor-input-plugin/` へ集約。
- 親リポジトリは submodule 管理前提であることを README に明記。
- App 側導入時は「親ではなく個別 plugin repo URL を指定」する運用を明記。

## 2. `UrlViewer-App` 側

### 変更ファイル
- `src/shared/schemas.ts`
- `src/electron/services/pluginManager.ts`
- `src/electron/ipc/handlers.ts`
- `src/electron/preload/index.ts`
- `src/web/vite-env.d.ts`
- `src/web/store/slices/registrationSlice.ts`
- `src/web/store/slices/uiSlice.ts`
- `src/web/store/pluginActions.ts`
- `src/web/plugins/registry.ts`
- `src/web/utils/mockApi.ts`

### 内容
- `pluginManager` が外部 input plugin を dynamic import して panel 取得・実行できるようにした。
- `plugins:resolveInput` IPC を追加し、Renderer はそこ経由で plugin input を実行。
- `plugins:listPanels` は runtime を解決できた input plugin のみ返すよう変更。
- Renderer 側の panel 計算をローカル固定 registry から IPC 取得へ変更。

## 3. 検証
- `UrlViewer-App`: `yarn typecheck` 成功
- `UrlViewer-Plugins`: `node` 実行で URL 抽出プラグインの動作確認成功
