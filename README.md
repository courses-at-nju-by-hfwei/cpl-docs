# CPL 课程文档仓库

## 须知

使用了 [docsify](https://docsify.js.org/#/zh-cn/) 的框架，目前部署在腾讯云上，通过 http://docs.cpl.icu/2023 访问。

基础语法为 Markdown，有部分 docsify 扩展语法与插件，项目配置文件为 [docs/index.html](docs/index.html)。

在服务器上部署该文档网页：（以下方法已弃用，已通过 nginx 部署）

````bash
    npm i docsify-cli -g
    npm i http-server -g
    git clone <本项目地址>
    cd /cpl-docs/docs/
    nohup http-server -p 80 &
    exit
````

更新时只需要 `git pull` 就可以热更新，不需要重启进程。

目前服务器使用定时任务，每十分钟更新一次。

在本地部署该文档网页：

````bash
    npm i docsify-cli -g
    git clone <本项目地址>
    cd /cpl-docs/
    docsify serve docs
````

往年的文档在不同分支下。