## 关于本笔记

overnote 系列笔记是我在平时一些学习时间阅读书籍博客、观看视频后整理出来的一套体系化的笔记，着重将一个整套知识体系由浅入深的记录下来，并做适当的横向扩展。

由于笔记刚刚开始整理，许多地方仍然没有体系化、详细化，笔误或者错误依然很多，敬请期待不断校正后的正式版。正式版会以类似 gitbook 的形式开放，便于阅读。

为何是笔记形式，而不是独立博客形式？

```
笔者引用并优化、扩展了很多优秀书籍内容。若不按目录主次写好，直接将这样的内容放在独立博客上，笔者认为是互联网的垃圾碎片

独立博客的内容目录极度不清晰，久而久之只能成为一个自己也不会问津的垃圾收集器。如果在平时学习中，学到了某个知识点，比如深入了解了闭包的用法，可以把心得通过git版本控制记录到笔记目录中对应的闭包章节，便于查找，而不是去博客上再次发一篇闭包文章，最终石沉大海。这样坚持下来，笔记就能越来越由浅入深，变得丰富。
```

## 新时代前端的学习方向要点

**需要深入的技术点**：

- 三大框架：Angular/Vue/React 的深入理解，精通其原理、周边生态！
- TypeScript：优秀的 JS 超集，可以体验一下面向接口设计的理念，当然 TS 也会因为 vue3.0 的普及而持续上升份额。
- 小程序：小程序已经很多年了，不算新，Taro、Uni-app 等第三方多端框架都可以试试。
- NodeJS：笔者认为：无 Node 不前端，o(╯□╰)o。
- 计算机基础：所有开发者都逃不掉的三大件：算法、操作系统、计算机网络

**需要实践的技术点**：

- Nest.js：NodeJS 后端服务框架，拥有完善 IOC 机制，可以提升前端的架构视野，当然阿里的 midway 也不错，这 2 个框架也是直接使用 TS 书写，可以加强 TS 学习
- Flutter：笔者认为是具有全新意义的跨平台框架
- GraphQL：
- Electron：快速构建跨平台应用的利器
- 持续集成：docker，CI/CD，甚至可以了解 k8s、Serverless

**可以简单了解的技术点**：

- PWA：简单关注即可，其技术原理也极其简单
- WASM：目前火热的 rust、go 等语言已经支持，可以尝试
- IOT：
- TensorFlow.js

## 资料

> 没有被录入的一部分书籍也并不代表他们不优秀，只是很多内容与下列推荐书籍重复了，每个技术尽量精读 1-2 本

### 网页与动画

- [《HTML5 与 CSS3 基础教程》第 8 版](https://book.douban.com/subject/25878992/)：HTML 与 CSS 基础入门
- [《CSS 揭秘》](https://book.douban.com/subject/26745943/)：重点书籍，CSS 书籍瑰宝！！！
- [《HTML5+JavaScript 动画基础》](https://book.douban.com/subject/24744218/)：目前最好的动画书籍
- [《HTML5 Canvas 核心技术》](https://book.douban.com/subject/24533314/)：目前最好的 canvas 书籍

### JavaScript

语法基础：

- [《JavaScript 高级程序设计》第 3 版](https://book.douban.com/subject/10546125/)：外号红宝书，笔者认为是最好的 JS 入门书籍
- [《JavaScript 语言精粹》修订版](https://book.douban.com/subject/11874748/)：外号蝴蝶书，是 JS 核心语法的荟萃，短小精悍
- [《JavaScript 权威指南》第 6 版](https://book.douban.com/subject/10549733/)：外号犀牛书，是一部 JS 的百科全书，过于庞大，有红宝书足矣

DOM 编程：

- [《JavaScript DOM 编程艺术》第 2 版](https://book.douban.com/subject/6038371/)
- [《锋利的 jQuery》第 2 版](https://book.douban.com/subject/10792216/)
- [《jQuery 技术内幕》](https://book.douban.com/subject/25823709/)

提升篇：

- [《JavaScript 忍者秘籍》第 2 版](https://book.douban.com/subject/30143702/)：对函数的讲解：闭包、重载、curry 化讲解极好
- [《JavaScript 核心技术开发解密》](https://book.douban.com/subject/30190189/)：短小精悍的介绍了一些难点
- [《你不知道 JavaScript》上卷+中卷](https://book.douban.com/subject/26351021/)：笔者认为目前最好的 JS 深入书籍之一
- [《JavaScript 设计模式与开发实践》](https://book.douban.com/subject/26382780/)
- [《JavaScript 模式》](https://book.douban.com/subject/11506062/)

ES6 篇：

- [《深入理解 ECMAScript6》](https://book.douban.com/subject/27072230/)
- [《ECMAScript6 入门》第 3 版](https://book.douban.com/subject/27127030/)

Vue：

- [《深入浅出 Vue.js》](https://book.douban.com/subject/32581281/)

React:

- [《深入 React 技术栈》](https://book.douban.com/subject/26918038/)
- [《深入浅出 React 和 Redux》](https://book.douban.com/subject/27033213/)
- [《React 状态管理与同构实战》](https://book.douban.com/subject/30290509/)

综合：

- [《高效前端：Web 高效编程与优化实践》](https://book.douban.com/subject/30170670/)
- [《高性能 JavaScript》](https://book.douban.com/subject/5362856/)
- [《了不起的 JavaScript 工程师：从前端到全端高级进阶》](https://book.douban.com/subject/34788884/)

### Node 书籍

- [《深入浅出 Node.js》](https://book.douban.com/subject/25768396/)：Node 书籍的集大成者，虽然一部分内容已过时，但仍然值得精读
- [《Node.js:来一打 C++扩展》](https://book.douban.com/subject/30247892/)：窥探 Node 底层的好书

### 其他技术

Electron：

- [《Electron 跨平台开发实战》](https://book.douban.com/subject/34838092/)
- [《Electron 实战：入门、进阶与性能优化》](https://book.douban.com/subject/35069275/)

## 附

**OverNote**地址：https://github.com/overnote  
**笔者的地址**：https://github.com/ruyuejun

**OverNote 分类**：

- [Golang](https://github.com/overnote/over-golang)：详尽的 Go 领域笔记：Go 语法、Go 并发编程、GoWeb 编程、Go 微服务等
- [大前端](https://github.com/overnote/over-javascript)：包含 JavaScript、Node.js、vue/react、微信开发、Flutter 等大前端技术
- [数据结构与算法](https://github.com/overnote/over-algorithm)：以 C/Go 实现为主记录数据结构与算法的笔记
- [服务端架构](https://github.com/overnote/over-server)：分布式与微服务笔记，附 Nginx、Mysql、Redis 等常用服务端技术
- [Python 与机器学习](https://github.com/overnote/over-python)：Python 相关笔记，完善中
- [Linux](https://github.com/overnote/over-linux)：计算机组成原理、操作系统、计算机网络、编译原理基础学科笔记
- [大数据](https://github.com/overnote/over-bigdata)：大数据笔记，完善中
- [flutter](https://github.com/overnote/over-flutter)
