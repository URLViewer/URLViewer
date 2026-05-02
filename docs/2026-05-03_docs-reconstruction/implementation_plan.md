# 実装計画

## 方針
1. 現行コードを一次情報として仕様を確定する。
2. 既存 docs は背景情報として参照し、現状との差分を吸収する。
3. 目的別に文書を分離し、運用手順と実装仕様を混在させない。

## 手順
1. ルート README / 各サブリポジトリ README を確認。
2. `UrlViewer-App` の実装を確認。
   - `src/electron/services/pluginManager.ts`
   - `src/electron/services/keychain.ts`
   - `src/electron/updater/provider.ts`
   - `src/electron/ipc/handlers.ts`
   - `src/web/features/plugins/PluginManagerPanel.tsx`
   - `src/shared/schemas.ts`
3. `.github/workflows/release.yml` と `package.json` の build/publish 設定を確認。
4. 既存 `docs/*` の release/private plugin 関連記録を統合。
5. 6本の統合ドキュメントを新規作成。
6. 作成内容を `walkthrough.md` に記録。

## 成功条件
- 要求された6テーマをそれぞれ独立した文書として参照できる。
- 手順記述が現行コードと矛盾しない。
- token の用途・保管場所・設定場所が明確化される。
