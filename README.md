# MyProfile

一个可拖拽编辑的静态个人主页 Hero 页面。项目基于原生 HTML、CSS 和 JavaScript 实现，无需构建工具，打开 `index.html` 即可使用。

## 功能特性

- 可视化编辑首页文案、链接、颜色、位置、旋转角度和动画延迟
- 支持拖拽页面元素，拖拽后自动同步到编辑面板
- 支持复制、下载和导入 JSON 配置，便于备份与复用
- 内置首屏入场动画，可在面板中开启、关闭或重播
- 包含头像、位置标签、访问按钮、短句和备案链接等个人主页常用模块
- 纯静态部署，适合 GitHub Pages、Cloudflare Pages、Vercel、Nginx 等环境

## 项目结构

```text
.
├── index.html                         # 当前主页入口，包含编辑面板与交互逻辑
├── Portfolio-Hero-Editor-Draggable.html # 旧版独立拖拽编辑器示例
├── README.md                          # 项目说明
└── css
    ├── style.css                      # 主页样式
    ├── img                            # 图标、头像与社交图标资源
    ├── js                             # 预留第三方脚本资源
    ├── font                           # APlayer 字体资源
    └── music                          # 预留音乐资源
```

## 快速开始

直接双击打开 `index.html`，或使用本地静态服务预览。

如果已安装 Node.js，可以在项目目录运行：

```bash
npx serve .
```

然后在浏览器访问命令行提示的本地地址。

也可以使用 VS Code 的 Live Server 插件打开项目根目录后预览 `index.html`。

## 使用说明

1. 打开 `index.html`。
2. 点击右上角 `打开编辑器`。
3. 在编辑面板中修改标题、位置、按钮文案、按钮链接、短句、颜色和动画参数。
4. 直接拖拽画布中的元素调整位置。
5. 使用 `复制 JSON` 或 `下载 JSON` 保存当前配置。
6. 后续可通过 `导入 JSON` 恢复配置。

## 常用自定义

### 修改基础文案

默认文案位于 `index.html` 的 `DEFAULT_CONFIG.text`：

```js
text: {
    title: 'MyProfile',
    home: 'HOME',
    location: '中国 · 河南',
    status: '访问主页',
    statusUrl: '/',
    beian: 'XICP备XXXX号',
    quote: '你惊艳了我的时光，也温柔了我的岁月。'
}
```

### 修改头像

默认头像路径为：

```html
<img src="./css/img/ico.png" alt="MyProfile 头像">
```

将自己的头像放入 `css/img/`，再替换 `src` 路径即可。

### 修改颜色

主题色在 `DEFAULT_CONFIG.colors` 中定义，也可以通过编辑面板修改：

```js
colors: {
    bg: '#d9dbdf',
    grid: 'rgba(0,0,0,0.045)',
    text: '#1f2827',
    blue: '#1736c6',
    yellow: '#f5ea18',
    white: '#ffffff'
}
```

### 修改布局

元素初始位置在 `DEFAULT_CONFIG.layout` 中定义，单位通常为 `px` 或 CSS 响应式表达式：

```js
title: { left: '70px', top: '214px', fontSize: 'clamp(78px,12vw,176px)', rotate: '0deg' }
```

推荐先通过页面编辑器拖拽调整，再复制 JSON 配置进行保存。

## 部署

这是纯静态项目，部署时上传以下文件即可：

```text
index.html
css/
```

如果使用 GitHub Pages，可以将项目推送到仓库后，在仓库设置中启用 Pages 并选择对应分支。

如果使用 Cloudflare Pages、Vercel 或 Netlify，构建命令留空，发布目录设置为项目根目录。

## 注意事项

- 项目依赖 Google Fonts，国内网络环境可能出现字体加载较慢的情况，可按需替换为本地字体或系统字体。
- `Portfolio-Hero-Editor-Draggable.html` 是旧版示例文件，正式主页以 `index.html` 为准。
- 当前主页已移除音乐播放器，但目录中仍保留部分历史音乐与播放器资源。
- 修改备案号时，请确保备案链接和备案文本符合实际备案信息。

## License

未指定许可证。如需公开分发或商用，请先补充明确的开源许可证。
