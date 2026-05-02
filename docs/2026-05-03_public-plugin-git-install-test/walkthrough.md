# 修正内容の確認

## 追加・変更ファイル
- `UrlViewer-Plugins/plugin.json`（新規）
- `UrlViewer-Plugins/dist/index.js`（新規）
- `UrlViewer-Plugins/src/index.ts`（新規）
- `UrlViewer-Plugins/.gitignore`（更新）
- `UrlViewer-Plugins/README.md`（更新）

## 実装内容
- プラグインID: `com.urlviewer.plugin.input.url-extractor`
- capability: `input-panel`
- 役割:
  - テキスト中の `http/https` URL を抽出
  - `url`, `src`, `redirect` などのクエリに埋め込まれたURLを再帰デコードして抽出
  - 重複を除外して URL 配列を返却

## 検証
以下コマンドで `dist/index.js` を直接実行し、抽出結果を確認。

```bash
node -e "(async()=>{const p=require('./dist/index.js'); const urls=await p.runtime.input.resolveToVideoSources('watch https://example.com/play?url=https%3A%2F%2Fcdn.example.com%2Flive.m3u8 and https://video.example.org/a.mp4'); console.log(urls);})()"
```

確認結果:
- plugin の読み込み成功
- 抽出URL 3件（直接URL2件 + クエリ埋め込みURL1件）
