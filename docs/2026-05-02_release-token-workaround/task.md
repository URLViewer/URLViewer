# task

## 目的
- `Read and write permissions` を選べない環境でも、自動リリースを継続可能にする。

## 実施項目
- [x] release workflow の publish トークンを `secrets.GITHUB_TOKEN` 依存から分離
- [x] `RELEASE_PAT` 未設定時に失敗原因が分かるバリデーションを追加

## 完了条件
- [x] workflow が `RELEASE_PAT` を使って `GH_TOKEN` を設定する
- [x] Secret 未設定時のエラーメッセージが明示される
