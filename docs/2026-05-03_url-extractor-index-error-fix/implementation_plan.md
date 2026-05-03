# 実装計画

1. `src/index.ts` のエラーを再現し、実際の診断メッセージを取得する。
2. `plugin.json` 直接 import に依存しないよう、manifest を `index.ts` 内で `PluginManifestV1` 型付き定数として保持する。
3. `Set` 依存を排除し、`Record<string, true>` で重複排除を行う実装へ置換する。
4. `yarn tsc --noEmit src/index.ts` でエラー解消を確認する。
5. `yarn build:js` を実行し、既存ビルドフローに回帰がないことを確認する。
