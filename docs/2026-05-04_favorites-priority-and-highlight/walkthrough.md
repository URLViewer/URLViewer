# 修正内容の確認

## 変更ファイル
- `src/web/features/groups/GroupPanel.tsx`
- `src/web/features/player/VideoPlayer.tsx`
- `src/web/styles/index.css`

## 変更内容
- `GroupPanel`
  - グループ配列のソートを favorites 優先に変更。
  - favorites 行のタイトル先頭に `star-solid`（黄色）を追加。

- `VideoPlayer`
  - 「グループへ追加」一覧の `displayedGroups` を favorites 優先でソート。
  - favorites 行に星アイコンを表示。
  - favorites 行に専用クラスを付与して視覚的に強調。

- `index.css`
  - `group-simple-item-label` を追加（星＋ラベルの横並び）。
  - `group-simple-item-favorite` を追加（薄いアンバー背景と境界で強調）。

## 検証
- `yarn typecheck`（`UrlViewer-App`）成功。
