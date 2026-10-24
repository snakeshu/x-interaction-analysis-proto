# 互动分析

免费、纯静态的 X（推特）互动分析工具（**非 X 官方**）。

- 公开页：https://snakeshu.github.io/x-interaction-analysis-proto/
- 数据：CSV 上传 / 粘贴，仅在浏览器本地解析，不上传服务器
- 能力：五视图、铁粉/粉丝/路人标签、分享卡 PNG、导出 CSV、示例数据
- 无付费墙、无后端、无 X OAuth

## 快速试用

1. 打开公开页，点「加载示例」或「导入数据」
2. 需要真数据时先「下载 CSV 模板」，填好后上传或粘贴
3. 在五视图里查看，可导出 CSV / 下载分享卡

## CSV 字段

必填：`handle`（用户名 / screen_name）、`they_replies`（对方回复数）、`i_replies`（我回复数）

可选：`name`、`preview_they`、`preview_i`、`last_their_at`、`wait_hours`

详见页面内导入说明或仓库根目录 `template.csv`。

## 计分

对方互动×2 + 我方×1 + 互关+1。串门回访用双向回复次数代理。

## 目录

- `index.html` — 当前产品（GitHub Pages 入口）
- `template.csv` — 导入模板
- `v1/`–`v4/` — 历史原型

## 本地预览

```bash
python3 -m http.server 8770
# http://127.0.0.1:8770/
```
