# implementation_plan

## 方針
1. `rcedit` が扱う EXE メタ情報を明示して、曖昧な推論を避ける。
2. まずローカルで `dist` 完走を確認し、CI 再実行前に失敗要因を減らす。

## 実装手順
1. `UrlViewer-App/package.json` の `build` を更新
   - `copyright` を ASCII 表記へ明示
   - `win.executableName` を明示
2. `yarn build`
3. `yarn dist`
4. 成功ログ（`rcedit` command executed）を確認
