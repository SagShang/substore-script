# substore-script

自用 `Sub-Store` / `mihomo(Clash Meta)` 配置与脚本仓库。

## 文件说明

- `Clash.yaml`：主路由配置，包含代理组、规则集、GEO 数据更新配置。
- `rename.js`：Sub-Store 节点重命名脚本，支持地区识别、倍率保留、前缀、国旗等参数。
- `ACL4SSR_Online_Full.yaml`：对照/参考配置。

## 快捷使用：

```text
https://raw.githubusercontent.com/SagShang/substore-script/main/Clash.yaml
```

## Clone

1. 将本仓库上传到你自己的 GitHub（或其他可直链访问的位置）。
2. 在 Sub-Store 脚本操作中使用 `rename.js` 的直链。
3. 在客户端使用 `Clash.yaml` 作为远程配置模板。

示例（按需替换仓库地址）：

```text
# GitHub Raw
https://raw.githubusercontent.com/<your-name>/<repo>/main/rename.js#in=zh&out=zh&flag&blgd&one

# GitHub Raw (CDN replacement)
https://raw.githubusercontent.com/<your-name>/<repo>/main/rename.js#in=zh&out=zh&flag&blgd&one
```

## rename.js 参数速查

- `in`：输入识别模式，支持 `zh/cn`、`en/us`、`flag/gq`、`quan`。
- `out`：输出命名模式，支持 `zh/cn`、`en/us`、`flag/gq`、`quan`。
- `nm`：保留未识别地区的节点。
- `flag`：给结果加国旗。
- `name`：添加统一前缀。
- `nf`：将 `name` 前缀放在最前面。
- `fgf`：字段分隔符（默认空格）。
- `sn`：国家名和序号的分隔符（默认空格）。
- `one`：仅有一个节点的地区去掉 `01`。
- `clear`：清理含无效关键词的节点名。
- `blgd`：保留固定标签（如 `IPLC`、`IEPL`、`GPT`、高倍标识）。
- `bl`：正则识别并保留倍率（如 `2x`、`3倍`）。
- `blnx`：仅保留高倍率节点。
- `nx`：过滤高倍率相关节点（仅保留 1x/无倍率）。
- `blpx`：对保留标签节点做分组排序（依赖 `bl`/`blgd` 使用更有意义）。
- `blkey`：保留自定义关键词，多个用 `+`，替换格式 `旧词>新词`。
- `blockquic`：`on/off`，控制节点 `block-quic` 字段。
