# 修正内容の確認

## 変更ファイル
- `src/web/store/appStoreTypes.ts`
- `src/web/store/libraryHelpers.ts`
- `src/web/store/slices/librarySlice.ts`
- `src/web/features/groups/GroupPanel.tsx`
- `src/web/features/library/VideoListItem.tsx`
- `src/web/features/player/VideoPlayer.tsx`

## 変更内容
- `buildLibraryForAddGroupWithVideo`
  - 既存グループの場合、未所属なら追加、所属済みなら除外するトグル挙動へ変更。
- `buildLibraryForRemoveVideoFromGroup` を追加。
- ストアに `removeVideoFromGroup(groupId, videoId)` を追加。
- GroupPanel の動画アイテム削除ボタン
  - 動画本体削除ではなく、`removeVideoFromGroup` を呼ぶよう変更。
  - ダイアログ文言を「この動画をグループから外しますか？」へ変更。
- `VideoListItem`
  - `deleteDisabled` props を追加し、文脈ごとに削除無効条件を上書き可能にした。
- VideoPlayer の「グループに追加」一覧
  - 追加済み項目の右ラベルを `解除` に変更。

## 挙動
- GroupPanel で動画行の削除ボタンを押すと、そのグループからのみ外れる。
- 「グループに追加」一覧では、未追加グループクリックで追加、追加済みグループクリックで解除。

## 検証
- `yarn typecheck`（`UrlViewer-App`）成功。
