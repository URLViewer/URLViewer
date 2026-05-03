# 修正内容の確認

## 変更ファイル
- `src/web/App.tsx`
- `src/web/styles/index.css`

## 変更内容
- `App.tsx`
  - `activityLogs` を監視し、新規ログ追加時の挙動を追加。
  - `success/error` ログ発生時にトースト表示。
  - トーストは自動消滅（3200ms）・手動クローズ対応。
  - ログ未読件数を状態管理し、ログパネル未表示中の新規ログで加算。
  - ログパネルを開くと未読件数をリセット。
  - ログボタンに未読バッジを表示（`99+` 上限表示）。

- `index.css`
  - `topbar-log-badge` を追加。
  - `app-toast`, `app-toast-success`, `app-toast-error`, `app-toast-close` などトースト用スタイルを追加。
  - `icon-btn` を `relative` 化してバッジの位置決めに対応。

## 挙動
- 成功・失敗の実行結果は画面右上にトーストで表示。
- ログパネルを開いていない間に新規ログが来ると、ログボタンに未読バッジが増加。
- ログパネルを開くと未読バッジは消える。

## 検証
- `yarn typecheck`（`UrlViewer-App`）成功。
