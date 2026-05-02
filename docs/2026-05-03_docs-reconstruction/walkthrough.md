# 修正内容の確認

## 実施内容
- 既存ドキュメント（root/docs, UrlViewer-App/docs）を横断し、重複記述を統合。
- 現行コードの挙動を基準に、次の6文書を新規作成。
  - `アプリ仕様書.md`
  - `リポジトリ構成説明書.md`
  - `プラグインシステム仕様と作成方法.md`
  - `プラグイン追加方法_public_private.md`
  - `デプロイ方法と仕組み.md`
  - `トークン取得方法と利用箇所.md`

## 反映した主な一次情報
- `UrlViewer-App/.github/workflows/release.yml`
- `UrlViewer-App/package.json`
- `UrlViewer-App/src/electron/updater/provider.ts`
- `UrlViewer-App/src/electron/services/pluginManager.ts`
- `UrlViewer-App/src/electron/services/keychain.ts`
- `UrlViewer-App/src/shared/schemas.ts`
- `UrlViewer-SDK/src/index.ts`

## 整理方針
- 過去 docs の実施記録は「履歴」として扱い、運用手順は現行構成に再定義。
- 要件書と実装差分がある箇所（例: capability や runtime 実装可否）は現行コード優先で記載。
- public/private token の使い分けを、設定場所・保存場所まで明示。
