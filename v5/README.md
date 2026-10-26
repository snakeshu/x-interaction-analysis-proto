# 互动分析 · 原型 v5

相对 product / v4：**入口改为 X 授权登录（演示）**，去掉 CSV 导入；**整站**使用用户提供的纸片层叠色系（粉 / 蓝 / 橙 / 玫红 / 黄）。未改 `v1/`–`v4/` 与 `product/`。

## 打开方式

```
file:///workspace/prototypes/x-interaction-analysis/v5/index.html
```

或：

```bash
cd /workspace/prototypes/x-interaction-analysis/v5
python3 -m http.server 8769
# http://127.0.0.1:8769/
```

手机请用父代理发布的公开链接。

## 怎么试登录 / 退出

1. 打开页面 → 落地页大按钮「使用 X 授权登录」
2. 弹出授权确认卡（只读权限示意）→ 点「授权并继续」
3. 写入 `sessionStorage.xia_v5_authed`，加载内置示例当作「已从 X 拉取」
4. 顶栏显示头像 / @handle、「已从 X 拉取 · 演示」、退出
5. 「退出」清除 session，回到落地页（同标签页刷新仍保持登录；关标签即掉）

多账号下拉文案为「切换已授权账号（演示）」——两套本地示例，非真 OAuth 多号。

## 相对 product 改动

- **删除** CSV 导入 / 粘贴 / 拖拽 / 模板下载 UI 与解析逻辑
- **入口**：X 授权登录演示（非真连 API）+「非 X 官方」标注
- **色系整站换肤**：`--coral #F18D8D` · `--sky #4DBBEB` · `--orange #F7941D` · `--magenta #E91E63` · `--yellow #FFD500`；顶栏条纹、按钮、标签、分享卡 chrome 同步
- 保留五视图、计分标签、分享卡、导出 CSV（登录后次要入口）
- localStorage / session 键：`xia_v5_account` · `xia_v5_weekly_on` · `xia_v5_authed`

## 已知局限

- 静态示例数据，无真实 X OAuth / API
- 授权仅为前端演示弹窗
- 多账号为两套本地数据切换
