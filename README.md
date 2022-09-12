# CPL 课程文档仓库

## 须知

使用了 [docsify](https://docsify.js.org/#/zh-cn/) 的框架, 目前部署在阿里云上, 通过 http://47.122.3.40/ 访问. 未来会绑定到域名 http://docs.cpl.icu/ 上.

基础语法为 Markdown, 有部分 docsify 扩展语法与插件, 项目配置文件为 [docs/index.html](docs/index.html).

在服务器上部署该文档网页: 

````bash
    npm i docsify-cli -g
    npm i http-server -g
    git clone <本项目地址>
    cd /cpl-docs/docs/
    nohup http-server -p 80 &
    exit
````

更新时只需要 `git pull` 就可以热更新, 不需要重启进程. 目前服务器使用定时任务，每小时更新一次.

在本地部署该文档网页: 

````bash
    npm i docsify-cli -g
    git clone <本项目地址>
    cd /cpl-docs/
    docsify serve docs
````

评论区使用了 [docsify-valine](https://github.com/daidi/docsify-valine/), 手册与文档均在该项目的 `README.md` 中, 需要注册 `leancloud` 账号并创建 `application` 来使用.

valine 评论区由于没有审核机制, 且删除评论需要到云服务器的数据库删除, 所以之后还是换成公共账号更好. 有记录 ip 的功能(但好像对 校园网 出口ip 来说没用). 怎样防止学生发布违禁内容仍需进一步探讨, 或者考虑换一个评论区插件. 目前希望学生能填写`南大邮箱`后再发表评论.

封面已部署, 但由于翻页插件的特性(bug), 从封面往下滑或者点击封面上的 "Get Start" 到达的第一页`课程简介`并没有翻页功能.

## Change Log

> 怎么办, 好像没人写了...

### Sakiyary @ 2022/9/6

在蚂蚁老师的基础上修改了一些小细节, 在 LOGO 上添加课程名称.

### hengxin @ 2022/9/6

修改了 `课程简介`, `教材与参考书籍`, `C 语言环境开发` 的内容与格式.

新增 `课程安排` 页.

### KYCoraxxx @ 2022/9/5

编写 `课程要求` - `提问与求助` 的内容.

### KYCoraxxx @ 2022/9/4

编写 `课程要求` - `代码风格与编程习惯` 的内容.

### Sakiyary @ 2022/9/4

重构目录结构, 清理掉了冗余图标. 

### 水龙之魂 @ 2022/9/4

由于域名备案需要时间, 故已尝试部署在 http://cpl.azifan.club/ 上.

### Sakiyary @ 2022/9/3

搭建 docsify 框架，部署至`阿里云`上开启公网访问.

将 `CPL课程必读&索引文档` 拆分成了多个 `.md` 文件 (即多个页面), 并删减掉部分冗余文档与 Typora 的扩展语法, 更改为了 docsify 的扩展语法.

补充了部分文档.

### Sakiyary @ 2022/8/23

完成 CPL课程必读&索引文档 的提纲. 

在还没有详细写完整的地方都补充了 `(TODO: something)`, 欢迎各位补充与校对. 