# タスク

## 背景
前回作成した public プラグインを `UrlViewer-Plugins` 直下に配置していたが、本来は `UrlViewer-Plugins/<plugin-name>` を個別リポジトリ（submodule）として管理する前提だった。

## 目的
1. `UrlViewer-Plugins` を submodule 親リポジトリの構成へ修正する。
2. `UrlViewer-App` で GitHub 由来の外部 input プラグインを導入後に実際に適用（実行）できるようにする。

## 実施項目
- [x] プラグイン配置を `url-extractor-input-plugin/` 配下へ移設
- [x] `UrlViewer-Plugins` README を submodule 前提へ修正
- [x] `UrlViewer-App` に外部 input plugin 実行IPC (`plugins:resolveInput`) を追加
- [x] `plugins:listPanels` を外部 runtime 反映型へ変更
- [x] Renderer 側の plugin 入力実行経路を IPC 呼び出しへ変更
- [x] 型チェック (`yarn typecheck`) を通過
