# Fuwari Typora 主题

[English Version](README.md)

这是一款受 [Fuwari](https://github.com/saicaca/fuwari)（一个基于 Astro 的静态博客模板）启发的 Typora 主题。

主题将 Fuwari 的视觉语言移植为 Typora 的纯 CSS：

- 柔和的卡片式写作区
- 受 Fuwari 启发的 OKLCH 调色板，默认色相 `250`
- 固定浅色模式主题
- 虚线下划线链接
- 圆角行内代码和浅色代码块
- 圆角图片、柔和引用块、虚线分隔线、高亮列表标记
- 对 Typora 侧栏、大纲、目录、源码模式、表格、任务列表、数学块和元信息的基础样式支持

## 文件

- `fuwari-light.css` - 固定浅色模式 Typora 主题，Typora 中显示为 `Fuwari Light`。
- `fuwari-assets/fuwari-base.css` - 主题文件引用的共享样式。请将该文件夹与 CSS 文件放在同一目录下。

## 安装

### 从 Release 安装（推荐）

1. 从 [Releases](https://github.com/Caph-dev/typora-fuwari-theme/releases/latest) 下载 `fuwari-light-v1.1.0.zip`。
2. 打开 Typora → `偏好设置` → `外观` → `打开主题文件夹`。
3. 解压 zip 文件，将 `fuwari-light.css` 和 `fuwari-assets/` 复制到主题文件夹中。
4. 重启 Typora，在 `主题` 菜单中选择 `Fuwari Light`。

### 从源码安装

克隆或下载本仓库，然后将 `fuwari-light.css` 和 `fuwari-assets/` 复制到 Typora 主题文件夹。

macOS 上 Typora 主题文件夹的典型路径：

```text
/Users/{用户名}/Library/Application Support/abnerworks.Typora/themes/
```

## 推荐字体

主题开箱即用，会回退到系统字体。安装以下字体可获得最佳体验：

| 用途 | 字体 | 链接 |
| --- | --- | --- |
| 正文 | Roboto | <https://fonts.google.com/specimen/Roboto> |
| 正文（备选） | Inter | <https://rsms.me/inter/> |
| 代码 | Maple Mono Normal NF CN | <https://github.com/subframe7536/maple-font> |
| 代码（备选） | JetBrains Mono | <https://www.jetbrains.com/lp/mono/> |

## 设计说明

CSS 为 Typora 手写编写，而非从 Fuwari 的 Tailwind 和 Stylus 源码复制。它将以下 Fuwari 设计理念映射到 Typora 选择器：

- `#write` 变为居中文章卡片，类似 Fuwari 的文章主体。
- `:root` 定义主题调色板，并将其映射到 Typora 变量，如 `--bg-color`、`--text-color`、`--primary-color`、`--side-bar-bg-color` 和 `--monospace`。
- 行内代码使用 `--fuwari-inline-code-bg`（浅蓝 `#e2f0ff`）和 `--fuwari-inline-code-color`。
- 代码块使用浅色"Slate Paper"配色方案——冷静克制的语法高亮，token 颜色区分明确。
- 链接使用 Fuwari 文章中的虚线下划线和柔和悬停背景。

主题不包含任何外部字体或图片。如果本地安装了 `Roboto` 或 `JetBrains Mono`，Typora 会自动使用它们；否则 CSS 会回退到系统字体。

## 兼容性

Typora 在 macOS 上基于 WebKit，在 Windows/Linux 上基于 Chromium。本主题使用了 `oklch()`、`color-mix()`、`clamp()` 和 `:has()` 等现代 CSS 特性。较新版本的 Typora 应能正确渲染。如果旧版本不支持部分调色板，请先更新 Typora。

## 自定义

要更改主题色，编辑 `fuwari-light.css` 中的以下变量：

```css
:root {
  --hue: 250;
}
```

示例：

- `200` - 青绿
- `250` - Fuwari 默认蓝紫
- `310` - 紫粉
- `345` - 粉红

## 在 Typora 中调试

如果需要微调主题：

1. 启用 Typora 调试模式。
2. 右键点击要检查的元素，选择 `检查元素`。
3. 在 `fuwari-light.css` 中调整调色板变量，在 `fuwari-assets/fuwari-base.css` 中调整共享选择器。
4. 重启 Typora 或来回切换主题以重新加载 CSS。

## 参考来源

- Fuwari 仓库：<https://github.com/saicaca/fuwari>
- Fuwari 演示：<https://fuwari.vercel.app/posts/expressive-code/>
- Typora 自定义主题指南：<https://theme.typora.io/doc/Write-Custom-Theme/>
- Typora 主题安装指南：<https://theme.typora.io/doc/Install-Theme/>
- Typora 样式文档：<https://support.typora.io/style/>

---

学 AI，上 LinuxDo <https://linux.do/>
