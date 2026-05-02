# タスク

## 目的
`UrlViewer-App` の Git 導入テストとして利用でき、かつ実運用でも有用な public プラグインを `UrlViewer-Plugins` に追加する。

## 実施項目
- [x] `plugin.json` をリポジトリ直下に追加
- [x] `entry` となる `dist/index.js` を追加
- [x] URL抽出系の実用 input plugin を実装
- [x] `README.md` にプラグイン概要を追記
- [x] `dist/index.js` を追跡できるよう `.gitignore` を調整

## 完了条件
- [x] Git導入の前提（`plugin.json` ルート配置）を満たす
- [x] プラグインが URL 候補抽出を返せる
