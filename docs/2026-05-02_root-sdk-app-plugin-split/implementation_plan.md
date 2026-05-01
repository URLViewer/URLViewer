# implementation_plan

## 方針
1. 先にリポジトリ境界を固定する（Root / SDK / App / Plugin）。
2. 次に SDK を App から切り離し、依存方向を `App -> SDK` に一本化する。
3. 最後に秘匿情報対策として、公開領域から非公開プラグイン痕跡を除去する。

## 実施手順
1. 各ディレクトリで `git init -b main` を実行。
2. 各リポジトリに `origin` を設定。
3. SDK を `UrlViewer-SDK` へ移動し、README / package 定義を整備。
4. App の `tsconfig` / `vite` からローカルSDK alias を削除。
5. App の `package.json` で SDK を GitHub URL 依存に切り替え。
6. 公開プラグインリポジトリから非公開プラグイン実体と痕跡を除去。
7. Root に `.gitmodules` を追加し、最終的な submodule URL を固定。

## 秘匿プラグイン対策
- 公開リポジトリに「名称」「ID」「リポジトリ名」「ディレクトリ名」を残さない。
- 公開 `UrlViewer-Plugins` にはポリシー文書のみを置く。
- 非公開プラグインは別 private リポジトリで管理し、Root には登録しない。
  - 必要な場合も、公開Rootの `.gitmodules` には記載しない。

## push までの前提
- `URLViewer` 組織配下に以下リポジトリを作成済みであること。
  - `UrlViewer`
  - `UrlViewer-App`
  - `UrlViewer-SDK`
  - `UrlViewer-Plugins`
- push 実行アカウントが上記リポジトリへ write 権限を持つこと。
