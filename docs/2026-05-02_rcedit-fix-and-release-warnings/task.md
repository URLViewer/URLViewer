# task

## 目的
- electron-builder 実行時の `rcedit` 失敗 (`Fatal error: Unable to commit changes`) を解消する。
- release ログに出ている warning の意味を整理する。

## 実施項目
- [x] `package.json` の Windows メタデータを明示化
- [x] `yarn dist` を実行して再現有無を確認

## 結果
- [x] `yarn dist` 成功
- [x] `rcedit` 実行成功をログで確認
