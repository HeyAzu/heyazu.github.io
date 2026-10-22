# 博客组件维护记录

更新日期：2026-10-22。

本仓库包含 Hexo 7.3.0 / Fluid 1.9.8 生成的静态网页，没有 PHP 或 WordPress 程序。当前没有 package.json、锁文件、Hexo 配置、主题源码或文章 Markdown 源文件，不能在本仓库直接重建 Hexo。

## 本次更新

| 组件 | 原版本 | 本次版本 | 位置 |
| --- | --- | --- | --- |
| jQuery | 3.6.4 | 3.7.1 | js/vendor/jquery-3.7.1.min.js |
| Bootstrap | 4.6.1 | 4.6.2 | css/vendor/bootstrap-4.6.2.min.css、js/vendor/bootstrap-4.6.2.bundle.min.js |
| Typed.js | 2.0.12 | 2.1.0 | js/vendor/typed-2.1.0.umd.js |

上述文件直接取自官方仓库的固定版本，保留原始内容及许可文本。42 个 HTML 页面统一引用本地副本；Bootstrap 使用带 Popper 的 bundle。其余 CDN 资源继续使用原配置。

站内搜索另外修复了两个问题：关键词按普通文字匹配，方括号、点号等不再被当作正则表达式；标题、摘要和链接属性中的文字在渲染前转义，拒绝非 HTTP(S) 结果链接。

## 兼容性与后续维护

- jQuery 3.7.1 是为了兼容当前主题选定的 3.x 版本，不代表最新主版本。Bootstrap 4.6.2 的官方 jQuery 依赖范围为 1.9.1 至 3.x。
- Bootstrap 4 已停止官方维护。4.6.2 是当前主题可兼容的补丁更新，不代表所有安全风险均已消除。升级至受维护的 Bootstrap 主版本需要连同 Fluid 模板、CSS 和 JavaScript 一起迁移并验证。
- Typed.js 2.1.0 保持现有 Typed 初始化方式；未迁移到新主版本。
- 未把生成器元信息改成新版本，也没有声称完成 Hexo / Fluid 源码升级。若从原始 Hexo 工程重新生成站点，需要将这些更改同步到原工程，否则会被覆盖。
- Fancybox、NProgress、Anchor.js、Clipboard.js、Tocbot、Markdown CSS 等资源本次未做全面升级或安全审计。

## 验证与回退

- 核对官方文件的 Git blob SHA；校验 42 个页面正文未被本次资源替换修改。
- 验证普通搜索、方括号、点号、连字符、空输入、HTML 文本转义和非 HTTP(S) 链接拒绝。
- 浏览器验证首页、搜索弹窗、文章搜索与文章页；本地预览缺少未下载的图片，原仓库图片不在修改范围内。
- 如需回退，撤销本次更新提交；原始 main 提交为 ae3a004e771f9b3b15b875c2a0d42e1f842f9d21。不要对后续已更新的 main 强制重置。

## 官方来源

- jQuery：<https://github.com/jquery/jquery-dist/tree/3.7.1>；<https://blog.jquery.com/2023/08/28/jquery-3-7-1-released-reliable-table-row-dimensions/>
- Bootstrap：<https://github.com/twbs/bootstrap/tree/v4.6.2>；<https://getbootstrap.com/docs/4.6/getting-started/download/>
- Typed.js：<https://github.com/mattboldt/typed.js/tree/v2.1.0>
- 许可文件：vendor-licenses/。

