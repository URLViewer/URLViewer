# task

## 目的
- `UrlViewer-App` で `yarn dev` が失敗する問題を解消する。
- `electron-builder` + `electron-updater` による自動リリース/自動アップデート基盤を整備する。
- リリース管理責務（`UrlViewer` vs `UrlViewer-App`）の方針を明確化する。

## 実施項目
- [x] `yarn dev` エラー再現と原因特定
- [x] ワークスペース名不整合（`m3u8-viewer@workspace:.`）解消
- [x] `ELECTRON_RUN_AS_NODE` 常駐環境での起動失敗対策
- [x] Electron main/ipc/store/service の import 方式修正
- [x] `electron-updater` 導入
- [x] 起動時更新確認・DL完了後再起動確認ダイアログ実装
- [x] `electron-builder` publish 設定追加
- [x] タグ push で GitHub Releases へ公開する workflow 追加
- [x] README に運用手順と環境変数を追記

## 完了条件
- [x] `yarn dev` が起動し、`electron.app.getPath` 例外が出ない
- [x] `yarn typecheck` 成功
- [x] `yarn build` 成功
- [x] 自動リリース workflow が repo 内に追加済み
