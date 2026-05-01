# implementation_plan

## 方針
1. 失敗の直接原因（`electron` の依存区分）を最優先で修正する。
2. ついでに CI 警告（Node20 deprecation）も同時に解消する。
3. 修正後は型チェックと本番ビルドで再発防止を確認する。

## 実装手順
1. `UrlViewer-App/package.json` を更新
   - `electron` を `devDependencies` へ移動
   - `description`, `author` を追加
2. `UrlViewer-App/.github/workflows/release.yml` を更新
   - `actions/checkout@v6`
   - `actions/setup-node@v6`
3. `yarn install`
4. `yarn typecheck`
5. `yarn build`
