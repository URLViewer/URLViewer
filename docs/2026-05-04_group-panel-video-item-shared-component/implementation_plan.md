# 実装計画

1. ライブラリ動画アイテム表示を `VideoListItem` として切り出す。
2. `VideoListItem` に以下の可変要素を props 化する。
   - 選択モード/選択状態
   - 再生/ロック/削除/名称変更ハンドラ
   - 所属グループ表示の有無
3. `LibraryPanel` の動画ループを `VideoListItem` 呼び出しへ置換する。
4. `GroupPanel` の展開動画一覧を `VideoListItem` 呼び出しへ置換し、`showGroupMembership=false` を指定する。
5. `GroupPanel` に動画削除確認ダイアログを追加し、ライブラリ側の挙動に揃える。
6. `yarn typecheck` で検証する。
