# walkthrough

## 実施結果
- `release.yml` を `RELEASE_PAT` ベースの publish に変更した。
- `RELEASE_PAT` が未設定の場合に、原因を明示して workflow を失敗させるステップを追加した。

## 変更ファイル
- `UrlViewer-App/.github/workflows/release.yml`

## 影響
- Organization 側で `Read and write permissions` を選べない場合でも、PAT 運用で自動リリースが可能。
- 設定漏れ時のデバッグコストが低減。
