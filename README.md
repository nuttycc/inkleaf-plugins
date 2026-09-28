# inkleaf-plugins

Inkleaf 的漫画源插件仓库。应用通过内置仓库 URL 拉取本仓库的 `index.json`，据此安装/卸载插件。

## 结构

```
index.json          插件索引（schemaVersion 1）
plugins/*.zip       插件包（manifest.json + main.js）
```

## 发布新插件或新版本

1. 把插件包 ZIP 放进 `plugins/`（文件名带版本号）。
2. 在 `index.json` 的 `plugins` 数组中新增/更新条目：`id`、`name`、`version`、`apiVersion`、`description`、`pkgUrl`（指向 ZIP 的 raw 链接）、`sha256`、`sizeBytes`。
3. `sha256` 与 `sizeBytes` 必须与 ZIP 实际值一致，应用安装前会校验。
4. git push 即发布。旧版本 ZIP 保留在 `plugins/` 中以支持回滚。

索引仓库 URL：`https://raw.githubusercontent.com/nuttycc/inkleaf-plugins/main/index.json`
