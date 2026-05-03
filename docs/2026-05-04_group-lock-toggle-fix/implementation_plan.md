# 実装計画

1. ストア型に `toggleGroupLock(groupId)` を追加する。
2. `libraryHelpers` にグループロックをトグルする関数を追加する（favorites は除外）。
3. `librarySlice` に `toggleGroupLock` アクションを実装し、保存・メッセージ・ログ更新を行う。
4. `GroupPanel` の各グループ行にロックボタンを追加し、ロック/解除をトグルする。
5. `favorites` はボタンを disabled にしてロック固定であることを明示する。
6. `yarn typecheck` で確認する。
