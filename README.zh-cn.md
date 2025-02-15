<p align="center">
  <a href="http://lcui.org/">
    <img src="https://lcui.lc-soft.io/static/images/lcui-logo-lg.png" alt="" width=72 height=72>
  </a>
  <h3 align="center">LCUI</h3>
  <p align="center">
    C 的图形界面开发库，可借助 XML 和 CSS 构建简单的跨平台桌面应用
  </p>
  <p align="center">
    <a href="https://travis-ci.org/lc-soft/LCUI"><img src="https://travis-ci.org/lc-soft/LCUI.png?branch=master" alt="Build Status"></a>
    <a href="https://coveralls.io/github/lc-soft/LCUI?branch=develop"><img src="https://coveralls.io/repos/github/lc-soft/LCUI/badge.svg?branch=develop" alt="Coverage Status"></a>
    <a href="http://opensource.org/licenses/MIT"><img src="https://img.shields.io/github/license/lc-soft/LCUI.svg" alt="License"></a>
    <a href="https://github.com/lc-soft/LCUI/releases"><img src="https://img.shields.io/github/release/lc-soft/LCUI/all.svg" alt="Github Release"></a>
    <a href="https://github.com/lc-soft/LCUI/releases"><img src="https://img.shields.io/github/downloads/lc-soft/LCUI/total.svg" alt="Github All Releases"></a>
    <img src="https://img.shields.io/github/repo-size/lc-soft/LCUI.svg" alt="Repo size">
    <img src="https://img.shields.io/github/languages/code-size/lc-soft/LCUI.svg" alt="Code size">
  </p>
</p>

## 目录

- [介绍](#介绍)
    - [主要特性](#主要特性)
    - [缺少的特性](#缺少的特性)
    - [相关项目](#相关项目)
    - [设计参考](#设计参考)
- [快速上手](#快速上手)
    - [Windows](#windows)
    - [Ubuntu](#ubuntu)
- [贡献](#贡献)
- [文档](#文档)
- [常见问题](#常见问题)
- [许可](#许可)

## 介绍

LCUI 是一个桌面端图形界面开发库，主要使用 C 语言编写，支持使用 CSS 和 XML 描述界面结构和样式，可用于构建简单的桌面应用程序。

### 主要特性

- **C 语言编写：** 适用于体积较小且主要使用 C 语言实现的应用程序，以及偏向使用 C 语言编写简单应用的开发者。
- **跨平台：** 支持 Windows 和 GNU/Linux 系统，可开发简单的 Windows 桌面应用和通用应用，以及 Linux 桌面应用。
- **XML 和 CSS 解析：** 使用 XML 和 CSS 来描述界面的结构和样式，易于开发和维护。
- **可缩放：** 支持全局缩放，支持使用基于屏幕密度的 sp 和 dp 单位表示界面元素的位置和大小。
- **图片处理：** 支持读取 jpg、png 和 bmp 格式的图片。
- **触控：** 支持多点触控，但目前只支持 Windows 系统。

### 缺少的特性

LCUI 的主要用途是方便作者开发简单的图形界面应用，简单也就意味着功能很少，比如：

- 没有硬件加速，图形渲染效率低下。
- 不支持剪切板，你不能选中和复制界面中的文本，也不能从其它程序复制文本到 LCUI 程序中。
- 输入法支持差，在 Linux 中仅支持输入英文字母和符号。
- 布局系统简单，不支持网格、表格等布局。

如今可参考的同类开源项目有很多，例如：[SDL](https://github.com/SDL-mirror/SDL)、[imgui](https://github.com/ocornut/imgui)，LCUI 中大部分缺少的特性都能在这些项目中找到相关实现，新功能的开发成本和复杂度也因此而降低了很多。开源此项目的目的之一是技术交流和分享，如果你有同类项目的研究和使用经验，可以考虑向此项目提供改进方案。

### 相关项目

想要了解 LCUI 具体能做什么？你可以查看以下项目：

- [LCUI CLI](https://github.com/lc-ui/lcui-cli) - 用于开发 LCUI 应用程序的命令行工具。
- [LCUI Router](https://github.com/lc-soft/lcui-router) - LCUI 的路由管理器，它提供类似于 [Vue Router](https://github.com/vuejs/vue-router) 的开发体验，能让你基于 LCUI 构建多视图的应用程序变得更简单。
- [LC Design](https://github.com/lc-ui/lc-design) — 专为 LCUI 开发的组件库，包含了一些通用组件和 css 样式。
- [LC Finder](https://github.com/lc-soft/LC-Finder) — 图片管理器，LCUI 的旗舰级应用程序，你可以将它作为参考对象，以此评估 LCUI 的性能、界面效果和开发复杂度是否符合你的需求。
- [Trad](https://github.com/lc-soft/trad) — 一个基于 JavaScript 语法且可编译为 C 的语言，预置 LCUI 绑定，提供类似于 [React](https://reactjs.org/) 的开发体验，能让你轻松基于 LCUI 创建响应式用户界面。

### 设计参考

- [SDL](https://github.com/SDL-mirror/SDL/tree/master/src/video/x11) — x11 的驱动代码参考
- [FreeType](https://www.freetype.org/freetype2/docs/design/design-3.html#section-1) — 数据结构的命名风格参考
- [LevelDB](https://github.com/google/leveldb/blob/master/include/leveldb/c.h) — 函数命名风格参考
- [jQuery](https://jquery.com/) — 部件操作接口的命名风格参考
- [MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS) — CSS 标准参考

## 快速上手

### Windows

使用 [lcui-cli](https://github.com/lc-ui/lcui-cli) 快速创建一个 LCUI 项目：

```shell
# 安装 lcui-cli
npm install -g @lcui/cli

# 创建一个名为 myapp 的 LCUI 项目
lcui create myapp

# 进入项目目录
cd myapp

# 运行这个项目
npm run start
```

或者，你可以从已有的[示例项目](https://github.com/lc-ui/lcui-quick-start)快速开始：

```shell
# 克隆示例代码库
git clone https://github.com/lc-ui/lcui-quick-start

# 进入代码库
cd lcui-quick-start

# 安装 NodeJS 依赖包
npm install

# 安装适用于 x64 CPU 架构的 C/C++ 依赖库
lcpkg install --arch x64

# 以调试模式运行应用程序
lcpkg run start --mode debug
```

想从零开始编写一个 LCUI 应用程序？你可以在你的项目目录里使用 [lcpkg](https://github.com/lc-soft/lcpkg) 来快速安装 LCUI：

```shell
# 初始化 lcpkg 配置文件，告诉 lcpkg 你的项目相关信息
lcpkg init

# 从 GitHub 下载安装已编译好的 LCUI 库
lcpkg install github.com/lc-soft/LCUI
```

安装成功后，按照 lcpkg 输出的帮助文档来配置你项目的编译参数。

如果你想手动从源码编译 LCUI，请在 LCUI 的源码目录中使用 lcpkg 安装依赖库：

```shell
lcpkg install
```

之后，使用 [Visual Studio](https://visualstudio.microsoft.com/) 打开 `build/windows/LCUI.sln` 文件，然后编译生成 LCUI。

### Ubuntu

```shell
# 安装依赖库
sudo apt-get install libpng-dev libjpeg-dev libxml2-dev libfreetype6-dev libx11-dev

# 克隆代码库
git clone https://github.com/lc-soft/LCUI.git

# 进入源码目录
cd LCUI

# 生成配置脚本
./autogen.sh

# 配置环境及构建工具
./configure

# 构建
make

# 如果需要安装的话
sudo make install

# 进入测试程序目录
cd test

#  运行 helloworld 程序
./helloworld
```

> **提示：** 如果需要自定义编译器、编译参数、安装位置等配置，请查阅 [INSTALL](INSTALL) 文件。

## 贡献

有很多方式可以为此项目的发展做贡献：

- [反馈问题](https://github.com/lc-soft/LCUI/issues)并在问题关闭时帮助我们验证它们是否已经修复
- 在源码中[搜索 FIXME 注释](https://github.com/lc-soft/LCUI/search?l=C&q=FIXME)，然后尝试解决它们
- 在 [IssueHunt](https://issuehunt.io/r/lc-soft/LCUI) 上为感兴趣的 issue 设置悬赏，吸引其他开发者参与开发
- 在 [OpenCollective](https://opencollective.com/LCUI) 上赞助此项目
- 审查[源代码的改动](https://github.com/lc-soft/LCUI/pulls)
- 修复已知问题

本项目采用了参与者公约定义的行为准则，该文档应用于许多开源社区，有关更多信息，请参阅[《行为准则》](CODE_OF_CONDUCT.zh-cn.md)。

## 文档

- 在线教程：[https://lcui.lc-soft.io/guide/](https://lcui.lc-soft.io/guide/)
- 更新日志：[CHANGELOG.zh-cn.md](CHANGELOG.zh-cn.md)

目前还没有 API 参考文档，你可以参考头文件、源代码、示例程序以及上述的相关项目来了解基本用法。

## 常见问题

1. **为什么开发它？**

   - 探索和实验新的 GUI 开发方式
   - 给职业生涯赚点加分项
   - 找点存在感
   - 打发时间

1. **这是一个浏览器内核吗？或者是像 Electron 这样的集成了浏览器环境的开发库？**

    不是，你可以当成是一个应用了部分 Web 技术的传统 GUI 开发库。

1. **我为什么要用 LCUI，而不是 Electron？**

    相较于功能完备的 Electron 而言，文件体积小、内存占用低并没有什么用，除了技术研究和交流外，你没有理由用 LCUI。

1. **适合哪些人使用？**

    适合有 GUI 应用开发经验、熟悉 Web 前端开发技术、有意向参与开源项目的 C 开发者使用，最好是具备两年 C 开发经验和一年 web 前端开发经验。以时间来衡量上手门槛可能有点模糊，以下按照技术方向分别列出了一些主要条件，你可自行判断自己是否能够快速上手。

    C：

    - 熟悉 C 语言及编译相关工具链的配置，能解决编译问题
    - 熟悉至少一种图形库和 GUI 库/框架，了解 GUI 应用程序的工作原理
    - 熟悉多线程编程，能够解决线程安全、线程同步等问题
    - 能熟练使用调试工具定位问题
    - 有较多的开源项目源码阅读经验

    Web 前端：

    - 熟练掌握常见布局
    - 熟悉 CSS 盒子模型和常用属性
    - 有良好的 CSS 编码风格

1. **和写网页一样吗？需要注意什么？**

    不完全一样，主要有以下差异需要注意：

    - 界面描述文件格式是 XML，与 HTML 有一点区别。
    - 本质上是在写 C 代码，开发效率比 JavaScript 低很多。
    - 没有 `<script>` 标签，你不能像 HTML 那样内嵌 JavaScript 或 C 代码。
    - 部件是基本的界面布局元素，不是文字，不支持图文混排，不存在 `inline` 显示类型。
    - 滚动条是一个独立的部件，使用 `overflow: scroll;` 样式不会自动出现滚动条，你需要主动创建它并指定容器和滚动层。
    - 所有文本由 TextView 部件渲染，它的显示类型为 `block` 而不是 `inline`。
    - 部件不会溢出父级部件的边界框，效果类似于已应用样式：`overflow: hidden;`。
    - 绝对定位的部件始终相对于其父级部件，而不是父级第一个非静态定位的部件。
    - 没有像 [Chrome Devtools](https://developers.google.com/web/tools/chrome-devtools) 这样的工具来调试图形界面，你需要凭借自己的想象力和开发经验来验证 BUG 是来自你的代码还是 LCUI 内部的。

1. **CSS 支持度如何？**

    以下是支持的 CSS 特性列表，已勾选的是表示已支持（至少支持基本功能），未列出的属性则默认不支持。

    <details>
      <summary>CSS 特性覆盖范围</summary>

      - at rules
        - [x] `@font-face`
        - [ ] `@keyframes`
        - [ ] `@media`
      - keywords
        - [ ] `!important`
      - selectors
        - [x] `*`
        - [x] `type`
        - [x] `#id`
        - [x] `.class`
        - [x] `:hover`
        - [x] `:focus`
        - [x] `:active`
        - [x] `:first-child`
        - [x] `:last-child`
        - [ ] `[attr="value"]`
        - [ ] `:not()`
        - [ ] `:nth-child()`
        - [ ] `parent > child`
        - [ ] `a ~ b`
        - [ ] `::after`
        - [ ] `::before`
        - [ ] ...
      - units
        - [x] px
        - [x] dp
        - [x] sp
        - [x] pt
        - [x] %
        - [ ] rem
        - [ ] vh
        - [ ] vw
      - properties
        - [x] top, right, bottom, left
        - [x] width, height
        - [x] visiblility
        - [x] display
          - [x] none
          - [x] inline-block
          - [x] block
          - [x] flex
          - [ ] inline
          - [ ] grid
          - [ ] table
          - [ ] table-cell
          - [ ] table-row
          - [ ] table-column
          - [ ] ...
        - [x] position
          - [x] static
          - [x] relative
          - [x] absolute
          - [ ] fixed
        - [x] box-sizing
          - [x] border-box
          - [x] content-box
        - [x] border
        - [x] border-radius
        - [x] background-color
        - [x] background-image
        - [x] background-position
        - [x] background-cover
        - [ ] background
        - [x] pointer-evnets
        - [x] font-face
        - [x] font-family
        - [x] font-size
        - [x] font-style
        - [x] justify-content
          - [x] flex-start
          - [x] center
          - [x] flex-end
        - [ ] float
        - [ ] transition
        - [ ] transform
        - [ ] flex
        - [ ] ...
    </details>

1. **我想要 ???? 功能，就像 ???? 里的那样。**

    请先[新建 issue](https://github.com/lc-soft/LCUI/issues/new/choose)，按照已有的模板补全内容。

1. **求添加 JavaScript/Python/Go/Rust/PHP/C#/Java 语言绑定**

    已有官方支持的 [Trad](https://github.com/lc-soft/trad) 语言绑定，不考虑添加其它语言绑定。如果你实在需要的话可以自己动手设计，毕竟你比作者更懂这些语言的编程思想和设计哲学，也算是一个展现技术实力的好机会。

## 许可

LCUI 采用的开源许可证是 [MIT](http://opensource.org/licenses/MIT)。
