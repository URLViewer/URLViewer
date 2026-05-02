# implementation_plan

## 方針
1. publish 処理は `refs/tags/v*` の時だけ実行する。
2. `workflow_dispatch` は配布物ビルド確認用途に限定する。
3. スクリプト側も `onTag` にして誤実行時の影響を防ぐ。

## 実装手順
1. `package.json` の `dist:publish` を `electron-builder --publish onTag` へ変更。
2. `release.yml` に `if: startsWith(github.ref, 'refs/tags/v')` 条件を追加。
3. `workflow_dispatch` 用に `Build Only` ステップを追加。
4. `yarn typecheck` / `yarn build` で検証。
