# 実装計画

## 1. 実装確認

- `PluginManagerPanel` の Git 導入 UI（URL / Branch / Token）を確認
- `pluginManager` の `installFromGit` / `update` 実装を確認
- `keychain` の token 保存方式を確認

## 2. ガイド化

- private リポジトリ導入の前提条件を定義
- UI での具体操作手順を定義
- token 作成時の最小権限を定義
- エラー時のチェックリストを定義

## 3. 制約明記

- 現在の renderer plugin registry が built-in 固定であることを明示
- 外部 plugin は導入できても実行不可になり得る点を明示
