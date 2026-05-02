# task

## 目的
- GitHub Release 作成時の 422 (`Published releases must have a valid tag`) を回避する。
- 手動実行 (`workflow_dispatch`) とタグ実行 (`push tags`) の挙動を分離する。

## 実施項目
- [x] `dist:publish` を `--publish onTag` に変更
- [x] workflow で publish をタグイベント限定に変更
- [x] 手動実行時は build-only に変更
