# 修正内容の確認

## 発生していたエラー
- `TS2732: Cannot find module '../plugin.json'`
- `TS2583: Cannot find name 'Set'`

## 変更内容
- `src/index.ts` で `plugin.json` の import を廃止し、`PluginManifestV1` 型付きの `manifest` 定数を定義。
- URL の重複排除を `Set<string>` から `Record<string, true>` に変更し、低い lib 設定でも型エラーが出ないように調整。
- それに合わせて重複判定ロジックを `unique.has(...)` から `unique[...]` 参照に置換。

## 検証結果
- `yarn tsc --noEmit src/index.ts` : 成功（エラー 0）
- `yarn build:js` : 成功
