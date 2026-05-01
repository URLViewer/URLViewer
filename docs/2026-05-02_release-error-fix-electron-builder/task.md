# task

## 目的
- GitHub Actions の release ジョブ失敗を解消する。
- `electron-builder` のエラー `Package "electron" is only allowed in "devDependencies"` を修正する。

## 実施項目
- [x] `package.json` で `electron` を `dependencies` から `devDependencies` へ移動
- [x] `description` / `author` を追加して builder warning を解消
- [x] Actions の Node20 廃止警告対策として `actions/checkout` と `actions/setup-node` を更新
- [x] `yarn install` / `yarn typecheck` / `yarn build` で検証
