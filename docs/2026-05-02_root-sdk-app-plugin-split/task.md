# task

## 目的
- `Root` / `SDK` / `App` / `Plugin` を独立Gitリポジトリとして分離する。
- すべてのリポジトリの push 先を `https://github.com/URLViewer/` 配下にそろえる。
- 非公開プラグインの存在や名称が公開リポジトリへ混入しないようにする。

## 実施項目
- [x] `UrlViewer` / `UrlViewer-App` / `UrlViewer-SDK` / `UrlViewer-Plugins` を個別に `git init`。
- [x] 4リポジトリの `origin` を `https://github.com/URLViewer/...` に設定。
- [x] SDK実体を `UrlViewer-App/packages/plugin-sdk` から `UrlViewer-SDK` へ移動。
- [x] App 側をローカルSDK同梱から外し、SDKリポジトリ依存へ変更。
- [x] 公開領域から非公開プラグイン痕跡を除去。
- [x] Root に submodule 定義ファイル（`.gitmodules`）を追加。

## 未完了（外部要因）
- [ ] GitHub 側リポジトリ作成
- [ ] 初回 commit / push
- [ ] Root の正式な `git submodule add` 完了（子リポジトリに commit が必要）
