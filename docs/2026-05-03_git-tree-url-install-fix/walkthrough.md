# 修正内容の確認

## 問題
- `plugins:installFromGit` が `payload.url` をそのまま `git.clone` に渡していた。
- GitHub の `https://github.com/.../tree/main/...` は clone URL ではないため、`isomorphic-git` が 404 を返していた。

## 変更
- `src/electron/services/pluginManager.ts` に `resolveGitInstallTarget` を追加。
  - GitHub URL の場合は clone URL を `https://github.com/<owner>/<repo>.git` に正規化。
  - `tree/<branch>/<subdir>` 形式では branch と subdir を抽出。
- `installFromGit` を修正。
  - 正規化した clone URL / branch を使って clone。
  - subdir 指定時はそのディレクトリを plugin root として導入。
  - subdir 指定時の sourceType は `folder` とし、更新ボタン（git pull）の対象外にする。
- `resolvePluginRootFromGitClone` を追加。
  - `path.relative` で repo 外参照（`..`）を拒否。

## 確認
- `yarn typecheck` : 成功
