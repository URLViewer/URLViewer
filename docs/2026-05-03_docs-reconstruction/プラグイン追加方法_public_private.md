# プラグイン追加方法_public_private

最終更新: 2026-05-03

## 1. 追加画面
アプリの「プラグイン」パネルには次の導入手段がある。

- ローカル導入
  - `ZIPから追加`
  - `フォルダから追加`
- Git導入
  - `Git URL`
  - `Branch (任意)`
  - `Token (private用)`

## 2. Public プラグイン追加手順

### 2.1 ZIP / フォルダ
1. プラグインパネルを開く。
2. `導入` タブで `ZIPから追加` もしくは `フォルダから追加` を選択。
3. 対象を選ぶ。
4. 成功時、一覧に追加され `導入: <plugin名>` メッセージが表示される。

### 2.2 Public Git リポジトリ
1. `Git URL` に公開リポジトリURLを入力。
2. 必要に応じて `Branch` を入力。
3. `Token` は空欄のまま `Gitから追加` を実行。

## 3. Private プラグイン追加手順

1. private リポジトリ読み取り可能な token を準備。
2. `Git URL` に private リポジトリURLを入力。
3. 必要なら `Branch` を入力。
4. `Token (private用)` に token を入力。
5. `Gitから追加` を実行。

成功時の挙動:
- clone 認証に token を利用。
- install 成功後、token は OS キーチェーンへ保存。
- 次回 `更新` 操作時は保存済み token を使って pull される。

## 4. 導入後にできる操作
- ON/OFF 切替
- 上下移動（表示順変更）
- `sourceType=git` のみ `更新`
- `builtin` 以外は `削除`

## 5. 失敗時の主な原因
- `duplicate-plugin-id`: 同じ `plugin.id` が既に存在
- `plugin.json` 不備: manifest schema 不一致
- `plugin-not-updatable`: git 由来でない plugin を更新しようとした
- `keychain-unavailable`: token 保存に必要な keychain が使えない

## 6. 運用上の注意
- built-in plugin は削除不可。
- private token はリポジトリや設定ファイルへ保存しない。
- 外部 `input-panel` は適用可能。
- 外部 `playback` は現時点では動的適用対象外（ビルトイン再生系のみ対応）。
