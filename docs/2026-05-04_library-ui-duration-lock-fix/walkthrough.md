# 修正内容の確認

## 1. 並び替えUI/ロジック
- `LibrarySortKey` を `"added" | "name" | "duration"` に拡張。
- `sortVideos` で `added` を実装。
  - 昇順: 現在の配列順（追加順）
  - 降順: 逆順
- `LibraryPanel` の並び替えUIを `追加順 / 名前 / 長さ` のピル型セグメントへ変更。

## 2. 動画長さの自動取得
- `videoDurationProbe.ts` を新規作成。
  - 非表示 `video` 要素で `loadedmetadata` を待ち、`duration` を取得。
  - タイムアウト/エラー時は未設定のまま継続。
- `registrationSlice` で登録完了後に新規追加動画のみ走査し、`setVideoDuration` で保存。
  - 通常入力登録
  - プラグイン入力登録
  - 検証実行（on-register/manual）

## 3. ロックボタン修正
- `buildLibraryForToggleVideoLock` を追加。
- `librarySlice` に `toggleVideoLock(videoId)` を追加。
- `LibraryPanel` の個別ロックボタンを有効化し、ロック/解除をトグル動作に変更。

## 4. アイテム表示崩れ修正
- `LibraryPanel` の各動画アイテムを
  - 先頭（状態/選択）
  - 中央（ラベル入力）
  - 右（再生/ロック/削除アクション）
  - 下段（バッジ・グループ）
  の構成に整理。
- `item-shell-video-simple` から `item-shell-video` へ変更し、アクション折り返しによる縦長崩れを解消。

## 5. スタイル追加
- `library-sort-shell`, `library-sort-chip`, `library-sort-order-btn`
- `library-item-leading`, `library-select-dot`

## 検証
- `yarn typecheck`（`UrlViewer-App`）成功。
