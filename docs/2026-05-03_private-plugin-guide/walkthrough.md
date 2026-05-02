# 修正内容の確認

## 実施内容

- private リポジトリ導入手順を、現行コードの挙動に基づいて整理
- 次のファイルを確認し、手順と制約を確定
  - `UrlViewer-App/src/web/features/plugins/PluginManagerPanel.tsx`
  - `UrlViewer-App/src/electron/services/pluginManager.ts`
  - `UrlViewer-App/src/electron/services/keychain.ts`
  - `UrlViewer-App/src/shared/schemas.ts`
  - `UrlViewer-App/src/web/plugins/registry.ts`

## 主要確認ポイント

- Git URL / Branch / Token を UI から入力して導入可能
- private 用 token は clone/pull 認証に使用され、成功時 keychain に保存される
- `plugin.json` はリポジトリ直下必須
- plugin id 重複時は導入拒否
- 現在は built-in runtime のみで、外部 plugin 実行は未配線
