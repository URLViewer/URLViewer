# implementation_plan

## 方針
1. Organization 制約で `GITHUB_TOKEN` が write 不可でも publish できるようにする。
2. リリース専用 PAT を Repository Secret に設定し、workflow で利用する。

## 実装手順
1. `.github/workflows/release.yml` に `Validate Release Token` ステップを追加。
2. `Build And Publish` の `GH_TOKEN` を `secrets.RELEASE_PAT` に差し替え。
3. Secret 未設定時は即失敗させ、設定漏れを明確化。
