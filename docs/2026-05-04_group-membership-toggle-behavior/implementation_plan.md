# 実装計画

1. グループ所属操作をトグル可能にするため、`buildLibraryForAddGroupWithVideo` を「追加/解除」挙動に変更する。
2. 指定グループから動画を外す専用ヘルパーとストアアクションを追加する。
3. GroupPanel の動画削除確認ダイアログを「グループから外す」用途に変更し、対象 groupId/videoId を保持する。
4. 共通動画アイテム `VideoListItem` に削除無効制御の上書き props を追加し、グループ文脈では動画ロックに依存しないようにする。
5. VideoPlayer の「グループに追加」一覧のステータス文言を `追加済み` から `解除` に変更する。
6. `yarn typecheck` を実行する。
