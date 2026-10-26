# 互动分析 · 原型 v7（肥皂泡）

相对 v6：气泡改成**透明肥皂泡**质感，空闲时轻微漂浮，初始布局**往画布中部错落集中**（仍保持高回复偏上、低回复偏下）。保留一屏无滚屏、可拖、顶栏菜单、X 授权演示、纸片彩。未改 `v1/`–`v6/` 与 `product/`。

## 打开方式

```
file:///workspace/prototypes/x-interaction-analysis/v7/index.html
```

或：

```bash
cd /workspace/prototypes/x-interaction-analysis/v7
python3 -m http.server 8771
# http://127.0.0.1:8771/
```

## 怎么试

1. 打开 →「使用 X 授权登录」→「授权并继续」
2. 进入画布：泡泡聚在**中间一团**，半透明高光，上下轻漂
3. **拖动**任意泡：漂浮暂停；松手后停在新位置并恢复漂浮
4. 点选打开底部详情；顶栏筛选铁粉·粉丝·路人
5. 页面本身**不滚屏**，人物缩进一框内

## 相对 v6 视觉改动

- **肥皂泡**：rgba 半透明 + 轻 `backdrop-filter`、高光弧 / 辅高光伪元素、细描边与柔阴影；标签用淡彩描边/晕染区分，不再实心色饼
- **漂浮感**：CSS `soap-float`，每泡不同 `--fx/--fy/--fdur/--fdelay`；`.dragging` 时 `animation: none`
- **中间错落集中**：布局在约 58%×64% 中央簇内落点，x 向中轴靠拢 + 黄金角错落；碰撞后仍软拉回分档 y
- 背景条纹略降透明度，画布中央加淡径向光，突出泡
- session 键：`xia_v7_authed` · `xia_v7_account`

## 已知局限

- 仍为静态示例 + 演示授权，无真 X OAuth / API
- 拖动后位置不持久（刷新重布局）
- 漂浮用 CSS transform，与拖动时的 `left/top` 叠加；极老浏览器可能无 backdrop-filter
- 人数多时中央簇会更挤，气泡变小
