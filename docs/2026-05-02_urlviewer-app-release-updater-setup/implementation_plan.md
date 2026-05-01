# implementation_plan

## 方針
1. 先に `yarn dev` を復旧し、開発サイクルを回せる状態に戻す。
2. その後に更新基盤（updater）と配布基盤（release workflow）を実装する。
3. 最後に README と docs へ運用ルールを明文化する。

## 設計

### 1. 開発起動の安定化
- 既存の `dev` スクリプト（`set ELECTRON_RUN_AS_NODE=&& vite`）はシェル依存で不安定。
- Node ラッパー `scripts/dev.mjs` で `process.env` から `ELECTRON_RUN_AS_NODE` を確実に削除してから `vite` を起動する。
- Electron API は default import を避け、named import を利用する。

### 2. 自動アップデート
- `src/electron/updater/provider.ts` を `Noop` から実装版へ拡張。
- `electron-updater` の `autoUpdater` を利用し、起動時に `checkForUpdates()`。
- 更新ダウンロード後はダイアログで再起動確認し、`quitAndInstall()` 実行。
- 開発時は既定無効、本番時有効（環境変数で上書き可能）。

### 3. 自動リリース
- `package.json` の `build.publish` を GitHub provider に設定。
- `dist:publish` スクリプトを追加。
- `.github/workflows/release.yml` を追加し、`v*` タグ push で build+publish を実行。

## 実装手順
1. `yarn install` で lock/state を再同期。
2. `scripts/dev.mjs` 追加、`package.json#scripts.dev` を更新。
3. Electron main/ipc/store/service の import 修正。
4. updater provider 実装と main 側接続。
5. package.json に publish 設定・依存追加。
6. release workflow 追加。
7. README へ運用情報追記。
8. `yarn typecheck` / `yarn build` / `yarn dev` で検証。
