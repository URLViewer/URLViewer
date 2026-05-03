# 実装計画

1. `PluginManager.installFromGit` の clone 呼び出しを確認し、URL無変換で 404 になる経路を把握する。
2. GitHub URL を解釈する `resolveGitInstallTarget` を追加し、以下を抽出する。
   - clone用URL（`https://github.com/<owner>/<repo>.git`）
   - branch（入力優先、未指定時は `tree/<branch>/...` から抽出）
   - plugin サブパス（`tree/<branch>/` 以降）
3. clone 後にサブパスを plugin root として導入する処理を追加する。
4. plugin root 解決時に repo 外参照を拒否する安全チェックを追加する。
5. `yarn typecheck` を実行して確認する。
