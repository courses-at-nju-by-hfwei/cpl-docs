# CPL 课程文档仓库

## 须知

### Sakiyary @ 2022/9/4

重构一下目录结构, 清理掉了冗余图标, 使之更清晰. 

建议用 http://47.122.3.40/#/0-intro/ 来访问, 若访问根域名, 部分插件会有 bug (翻页插件在根域名页面不显示).

目前还需要在服务器上手动部署更新, GitHub Action 不会写, 坐等浇浇自动部署.

在服务器上部署该文档网页的指令: (使用 npm 包管理器)

````bash
    npm i docsify-cli -g
    npm i http-server -g
    git clone <本项目地址>
    cd /cpl-docs/docs/
    nohup http-server -p 80 &
    exit
````

更新时只需要 `git pull` 就可以热更新, 不需要重启进程.

### shuilongzhihun @ 2022/9/4

由于域名备案需要时间, 故先部署在 http://cpl.azifan.club/ 上.

### Sakiyary @ 2022/9/3

搭建了 [docsify](https://docsify.js.org/#/zh-cn/) 的框架, 并在部署至`阿里云`上开启公网访问, http://47.122.3.40/, 未来会绑定至域名 http://doc.cpl.icu/.

目前将 `CPL课程必读&索引文档` 拆分成了多个 `.md` 文件 (即多个页面), 并删减掉部分冗余文档与 Typora 的扩展语法, 更改为了 docsify 的扩展语法.

补充了部分文档.

### Sakiyary @ 2022/8/23

目前已完成~~[CPL课程必读&索引文档](https://github.com/courses-at-nju-by-hfwei/c-pl-docs/blob/main/CPL-Must-read-Index-Doc.md)~~ (该链接已失效) 的提纲, 用 Typora 编写并使用了其扩展语法 (如 Highlight 语法`==something==`), 在 GitHub 上无法渲染. 

在还没有详细写完整的地方都补充了 `(TODO: something)` , 欢迎各位补充与校对. 

不必在文档内直接写满教程, 我觉得应该是贴点链接. 毕竟是索引文档, 写一些指引性的话语就可以. (课程要求之类的需要补充完整)

我也夹带了一些私货, 都是我自己主观上觉得很好用的东西, 希望能跟新生们分享!