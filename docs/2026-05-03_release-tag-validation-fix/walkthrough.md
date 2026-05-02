# walkthrough

## 変更内容
- `UrlViewer-App/package.json`
  - `dist:publish` を `electron-builder --publish onTag` へ変更
- `UrlViewer-App/.github/workflows/release.yml`
  - publish トークン検証と publish ステップをタグ実行時のみに制限
  - `workflow_dispatch` は `yarn dist` の build-only に変更
  - `Print Release Context` を追加して event/ref を可視化

## 効果
- タグが無い実行で Release 作成 API が呼ばれず、422 を回避できる。
- タグ push 時のみ自動リリースが実行される。

## 検証
- `yarn typecheck`: 成功
- `yarn build`: 成功
