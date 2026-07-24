# Dawn Owl Light

一个基于 [Night Owl Light](https://github.com/sdras/night-owl-vscode-theme)(作者 Sarah Drasner)的浅色 VSCode 主题。在原样保留 Night Owl Light 语法配色的基础上,叠加了**经典深灰活动栏 + 蓝色状态栏**,以及**圆角 / 活动-非活动高度差标签**等美化。

## 特性

- **语法配色**:照搬 Night Owl Light —— 关键字紫 `#994cc3`、函数蓝 `#4876d6`、数字品红 `#aa0982`、注释灰斜体 `#989fb1`
- **字符串**:由原版酒红 `#c96765` 改为舒适高对比的绿 `#22863A`(v0.5)
- **经典两栏**:活动栏深灰 `#333333`、状态栏蓝 `#007ACC`
- **标签页**:活动标签与编辑区融合 + 顶部蓝条,非活动标签压暗(v0.3+)
- **v0.4 增强 token**:彩虹括号、活动缩进线、Sticky Scroll 配色、括号配对高亮、符号图标配色、minimap / 滚动条 accent、inlay hint 柔化等
- **可选**:圆角 + 活动标签满高 / 非活动标签矮一截(需 custom-css 扩展注入 `custom.css`)

## 安装

```powershell
code --install-extension dawn-owl-0.5.0.vsix --force
```

安装后 `Ctrl+K Ctrl+T` 选择 **Dawn Owl Light**。

## 推荐设置(获得最佳效果)

```jsonc
"editor.bracketPairColorization.enabled": true,
"editor.bracketPairColorization.independentColorPoolPerBracketType": true,
"editor.guides.bracketPairs": true,
"editor.guides.highlightActiveIndentation": true,
"editor.cursorBlinking": "smooth",
"editor.cursorSmoothCaretAnimation": "explicit",
"editor.smoothScrolling": true,
"editor.minimap.renderCharacters": false,
"editor.scrollbar.verticalSliderSize": 10,
"editor.renderLineHighlight": "all",
"editor.stickyScroll.enabled": true,
"window.titleBarStyle": "custom",
"window.dialogStyle": "custom"
```

## 可选:圆角 + 高度差标签

VSCode 只开放标签颜色,不开放圆角与每标签高度。要实现需向 workbench 注入 CSS:

1. 安装 [Custom CSS and JS Loader](https://marketplace.visualstudio.com/items?itemName=be5invis.vscode-custom-css)
2. 在 `settings.json` 指向 `custom.css`:
   ```jsonc
   "vscode_custom_css.imports": ["file://${workspaceFolder}/custom.css"]
   ```
3. **以管理员身份**运行 VSCode → 命令面板 `Enable Custom CSS and JS` → 重启
4. 若提示 "corrupted",点 **Don't show again**

> 每次 VSCode 升级或改了 `custom.css`,需重新 `Reload Custom CSS and JS`(管理员)+ 重启。

## 调色板

| 角色 | 颜色 |
|---|---|
| 编辑器背景 | `#FBFBFB` |
| 正文 | `#403f53` |
| 关键字 | `#994cc3` |
| 字符串 | `#22863A` |
| 函数 | `#4876d6` |
| 数字 / 常量 | `#aa0982` |
| 注释 | `#989fb1` |
| 活动栏 | `#333333` |
| 状态栏 | `#007ACC` |

## 开发

```powershell
# 调试:在仓库根目录按 F5 启动扩展开发宿主
# 打包:
npx --yes @vscode/vsce@latest package --no-dependencies --allow-missing-repository
```

## 版本

- `0.5.0` 字符串色由酒红改为绿 `#22863A`(含模板 `${}` 插值)
- `0.4.0` 新增彩虹括号 / Sticky Scroll / 活动缩进线 / 符号图标等 token
- `0.3.x` 标签页配色增强(活动融合 + 蓝条 + 非活动压暗)
- `0.1.0` 初始版本

## 致谢

基于 [Night Owl](https://github.com/sdras/night-owl-vscode-theme) by Sarah Drasner。

## License

MIT
