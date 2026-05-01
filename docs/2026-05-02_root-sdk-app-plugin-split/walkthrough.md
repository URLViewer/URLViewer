# walkthrough

## 実施内容

### 1. リポジトリ分離
- `UrlViewer`
- `UrlViewer-App`
- `UrlViewer-SDK`
- `UrlViewer-Plugins`

上記4ディレクトリをそれぞれ独立Gitリポジトリとして初期化しました。

### 2. Remote設定
各リポジトリに以下を設定済みです。
- `https://github.com/URLViewer/UrlViewer.git`
- `https://github.com/URLViewer/UrlViewer-App.git`
- `https://github.com/URLViewer/UrlViewer-SDK.git`
- `https://github.com/URLViewer/UrlViewer-Plugins.git`

### 3. SDK切り出し
- `UrlViewer-App/packages/plugin-sdk` を `UrlViewer-SDK` に移設。
- App 側からローカルSDK alias を削除し、GitHub SDK依存へ切替。
  - `tsconfig.json`
  - `vite.config.ts`
  - `package.json`

### 4. 秘匿プラグイン対策
- 公開領域から非公開プラグイン実体を削除。
- 名称混入リスクがある文書を削除・置換。
- `UrlViewer-Plugins` は公開可能範囲の方針文書のみを保持。

### 5. Root整備
- `README.md` を追加（submodule運用手順とセキュリティ方針）
- `.gitmodules` を追加（App/SDK/PluginsのURLを定義）

## 確認結果
- 公開領域で非公開プラグイン固有語の再検索を行い、ヒットなし。

## 未完了事項
- GitHub 側リポジトリが未作成（`repository not found`）。
- `gh` の認証トークンが無効（再ログインが必要）。
- 子リポジトリ未commitのため、`git submodule add` は最終確定未実施。

## 仕上げコマンド（ユーザー実行用）
1. GitHubで4リポジトリ作成後、各子リポジトリで初回commit/pushを実施。
2. Root で以下を実行。

```bash
git submodule add -f https://github.com/URLViewer/UrlViewer-App.git UrlViewer-App
git submodule add -f https://github.com/URLViewer/UrlViewer-SDK.git UrlViewer-SDK
git submodule add -f https://github.com/URLViewer/UrlViewer-Plugins.git UrlViewer-Plugins
git submodule sync --recursive
```
