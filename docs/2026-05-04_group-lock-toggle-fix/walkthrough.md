# 修正内容の確認

## 変更ファイル
- `src/web/store/appStoreTypes.ts`
- `src/web/store/libraryHelpers.ts`
- `src/web/store/slices/librarySlice.ts`
- `src/web/features/groups/GroupPanel.tsx`

## 変更内容
- `AppState` に `toggleGroupLock(groupId)` を追加。
- `buildLibraryForToggleGroupLock` を追加。
  - 通常グループ: `locked` をトグル。
  - `builtin === "favorites"`: 変更しない。
- `librarySlice` に `toggleGroupLock` 実装。
  - 保存・メッセージ更新・ログ追加。
- `GroupPanel` 各グループ行に個別ロックボタンを追加。
  - ロック時: 鍵アイコン（lock）
  - 非ロック時: 開錠アイコン（unlock）
  - `favorites` は disabled + ツールチップで「ロック固定」を表示。

## 検証
- `yarn typecheck`（`UrlViewer-App`）成功。
