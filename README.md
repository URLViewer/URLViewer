# UrlViewer

`UrlViewer` は、複数リポジトリを submodule で束ねるルート（meta）リポジトリです。

## 構成
- `UrlViewer-App`: アプリ本体
- `UrlViewer-SDK`: プラグイン契約SDK
- `UrlViewer-Plugins`: 公開可能なプラグインのポリシー/配布管理

## clone
```bash
git clone --recurse-submodules https://github.com/URLViewer/UrlViewer.git
```

## 更新
```bash
git submodule sync --recursive
git submodule update --init --recursive
```

## セキュリティ方針
- 非公開プラグインの名称・識別子・実体は、このルートリポジトリに含めません。
- 非公開プラグインは private リポジトリで分離管理します。
