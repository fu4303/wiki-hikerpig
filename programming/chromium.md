Chromium
===

## 阅读源码

一个 CPP 苦手前端工程师的挣扎。

一些准备:

- [Checking out and building Chromium for Mac](https://chromium.googlesource.com/chromium/src/+/master/docs/mac_build_instructions.md)
- 学习 google 的构建工具 GN 的用法 [GN Quick Start guide](https://gn.googlesource.com/gn/+/HEAD/docs/quick_start.md)
- 在 Clion 中查看和构建 Chromium 项目, https://chromium.googlesource.com/chromium/src/+/master/docs/clion.md
- 在线看代码推荐使用 [Chromium Code Search](https://source.chromium.org/chromium/chromium/src/+/master:)

个人用到的一些工具:

- Code Browser [[sourcetrail]]

#### 参考文章

- [怎么去阅读Chromium的源码？](https://www.zhihu.com/question/306408034)

以下是一些官方文档：

- [Getting Around the Chromium Source Code Directory Structure - The Chromium Projects](https://sites.google.com/a/chromium.org/dev/developers/how-tos/getting-around-the-chrome-source-code) 。阅读代码库和开发的新手指南。
- [How Chromium Displays Web Pages - The Chromium Projects](https://sites.google.com/a/chromium.org/dev/developers/design-documents/displaying-a-web-page-in-chrome)。
- [Life of a Pixel - Google 幻灯片](https://docs.google.com/presentation/d/1boPxbgNrTU0ddsc144rcXayGA_WF53k96imRH8Mp34Y/edit)

### 读代码备忘

多进程结构中，进程和线程的大致分类和职责，[Multi-process Architecture - The Chromium Projects](https://sites.google.com/a/chromium.org/dev/developers/design-documents/multi-process-architecture)

![](https://sites.google.com/a/chromium.org/dev/_/rsrc/1220197832277/developers/design-documents/multi-process-architecture/arch.png)

- `browser`/`renderer` 在不同顶层文件夹里都有，指的是在对应 Process 里运行的代码。有 `common` 的话指的是他们之间共享的部分


### 安装和编译踩坑

#### 1. 运行 autoninja, 出现错误 no such package: infra/python/wheels/psutil/mac-amd64_cp32_abi3

见 [这个讨论](https://groups.google.com/a/chromium.org/g/chromium-discuss/c/ygXltbD3gLQ?pli=1) ，使用 pyenv 确保 shell 版本为 python2 即可（P.S. 尝试了 asdf，执行 gclient runhooks 阶段会莫名其妙出错，怀疑是其 shim 的方式与此项目不太兼容，放弃了）。


### 其他工具
- [强大的可视化利器 Chrome Trace Viewer 使用详解 - An Explorer](https://limboy.me/2020/03/21/chrome-trace-viewer/)
- [Chrome Tracing for Fun and Profit - Slack Engineering](https://slack.engineering/chrome-tracing-for-fun-and-profit/)