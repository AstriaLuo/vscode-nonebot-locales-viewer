# NoneBot2 Locales Viewer

> 用于显示 [nonebot-plugin-locales](https://github.com/goldsheep3/nonebot-plugin-locales) 的本地化文本预览的 VSCode 扩展。

## 快速开始

1. 安装扩展
2. 打开使用了 nonebot-plugin-locales 的工程文件
3. 打开 Python 文件后，`reply("rc.help")` 这类调用中的本地化键会显示为对应译文；源码不会被修改。

默认会尝试以静态识别 `locales_init(...)` 指向的语言目录；无法识别时，会回退到工作区的 `assets/lang` 目录。
将光标置于翻译键上时，会暂时显示原始键，便于编辑；鼠标悬停可查看键名与预览文本。

若当前预览的语言代码中没有该键的文本，会显示 `NO TRANSLATION!!!`。

## 配置项

| 设置 | 默认值 | 说明 |
| --- | --- | --- |
| `nonebotLocalesViewer.localeDirectory` | 空 | 语言目录，相对工作区根目录。留空时自动识别 `locales_init(...)`；手动设置优先级最高。 |
| `nonebotLocalesViewer.language` | `zh_CN` | 每个语言目录首次打开时的默认选择。之后可通过状态栏切换；选择会按目录独立保存。支持的情况依托于所在的 nonebot-plugin-locales 插件。 |
| `nonebotLocalesViewer.replyFunctions` | `["reply"]` | 需要识别的本地化函数名；函数的第一个字符串参数视为键。 |
| `nonebotLocalesViewer.displayMode` | `inline` | `inline` 视觉替换键；`after` 在键后显示译文。 |
| `nonebotLocalesViewer.previewColor` | 空 | 预览文字颜色。留空时使用当前主题的字符串色；可填写 CSS 颜色值，如 `#98c379`。 |

可执行命令面板中的 `NoneBot2 Locales Viewer: Refresh previews` 手动刷新。

打开 Python 文件时，状态栏会显示当前预览语言（例如 `$(globe) zh_CN`）。点击它可选择当前语言目录中的任意 YAML 语言文件。

## 更新历史

### 2026-11-06 v0.1.0

*Support: nonebot-plugin-locales@v0.2.0*

初始化仓库并实现基础显示功能。
