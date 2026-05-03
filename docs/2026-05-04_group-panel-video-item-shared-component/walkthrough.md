# 修正内容の確認

## 追加
- `src/web/features/library/VideoListItem.tsx`
  - ライブラリ動画アイテムの共通UIコンポーネントを新規追加。
  - `showGroupMembership` フラグで所属グループ表示領域の表示/非表示を切替可能。

## 変更
- `src/web/features/library/LibraryPanel.tsx`
  - 既存の動画アイテム描画ロジックを `VideoListItem` 利用へ置換。
  - 既存の再生・ロック・削除・名前変更の動作は維持。

- `src/web/features/groups/GroupPanel.tsx`
  - グループ展開時の動画表示を `VideoListItem` 利用へ置換。
  - `showGroupMembership={false}` を指定し、所属グループ表示領域のみ非表示化。
  - 動画削除確認ダイアログ（個別）を追加。
  - 再生は `openVideoTab + requestPlaybackCommand` でライブラリと同じ挙動へ統一。

## 検証
- `yarn typecheck`（`UrlViewer-App`）成功。
