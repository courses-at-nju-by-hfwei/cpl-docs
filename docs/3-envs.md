# C语言环境配置 ! ! !

?> **此为本课程最最重要的前置任务, 也是第一个让同学们去动手实践的任务!**

## 选择你的编程平台

你会选 **IDE** 还是 **"文本编辑器"** ? :sunglasses:

**IDE** ("Integrated Development Environment" 的简称, 意为"集成开发环境") 通俗点讲就是**代码编辑器、编译器、调试器和图形用户界面**的多合一. 

**"文本编辑器"**, 顾名思义, 用来写文本的. 之所以打上引号, 是因为编程时用的"文本编辑器"一般都会有相应的功能, 而不是像 `Microsoft Office Word` 那样的编辑器, 但其功能相对 IDE 又缺乏了许多.

### 本课程**推荐**使用:

[![CLion LOGO](.assets/images/Clion.svg ':size=32') -> **CLion**](https://www.jetbrains.com/clion/) (由 Jetbrains 开发的 C语言 IDE, 全平台使用)

[![VS Code LOGO](.assets/images/Visual_Studio_Code_1.35_icon.svg ':size=32') -> **Visual Studio Code**](https://code.visualstudio.com/) (简称 "VS Code",  由 Microsoft 开发的开源"文本编辑器")

?> 魏老师上课会使用 **CLion** 来进行课程演示与讲解 

(不过魏老师用的是 Linux 系统下搭载 Vim 插件的 CLion, 看不懂这两个名词没关系, 下面会讲到).

### **不作推荐但是可以**使用:

- Xcode (由 Apple Inc 开发的 macOS 专属 IDE)

- Dev-C++ (很古老的 IDE, 功能不够全但足够应付本课程)

- Visual Studio 20?? (简称 "VS", 由 Microsoft 开发的 IDE, 和上文的 VS Code **完全不同**, 有些庞大臃肿, 编译运行方式与 CLion 不同)

- 纯 Vim (需要特殊操作手法的文本编辑器, 由于需要熟练运用[特殊的操作](https://oi-wiki.org/tools/editor/vim/)才能高效写代码, 故上手难度极高, 很不友好. <small>但是魏老师就很会用 Vim 的操作手法!</small>)

- Sublime 、Notepad++、记事本、~~Microsoft Office Word~~ (都是文本编辑器)

### So...

你可以只配置一个编程平台, 也可以都去尝试尝试 (包括不作推荐的几款), 比较一下孰优孰劣, 归根结底还是**哪个顺手用哪个**. <small>~~:raised_hand:会者不难~~</small>

?> 如果想更容易地跟上老师的节奏, 那么就选 **CLion** 吧!

## 不同系统配置环境

鉴于同学们会使用**不同操作系统**的电脑/笔记本, 此处将会分别讲述.

<!-- tabs:start -->

## **Windows**

相信大部分同学都使用的微软 (Microsoft) 的 Windows 系统. 如果同学们的电脑是新购置的话, 很大概率预装了 `Windows 11` 新系统. 

相比 `Windows 10` , `Windows 11`最大的变化还是 UI ("User Interface" 的简称, 意为"用户界面") 的变化, 在配置环境这一步的具体操作上并没有太大的区别. 

本课程2022年录制的教程均以 `Windows 11` 系统来做演示, 以满足大部分买新电脑的同学们的体验.

### 1. Windows 里配置环境最重要的前提条件--用户目录名

(TODO: 强调不能中文用户目录名, 查看用户目录名的方法)

!> **请在确保自己电脑的用户目录名为英文的前提下, 再进行后续步骤操作!**

[Windows 更改用户名文字教程 (2022年编写整理)](https://www.yuque.com/itxia/help/change_win_account_name) 出自友社 *IT侠互助协会*. 

若同学们动手能力强, 可通读上述教程后慢慢地仔细地操作自己的电脑并更改用户名; 若害怕将自己的电脑弄坏 <small>(自己第一次上手的话弄坏概率不小)</small>, 欢迎在[南京大学IT侠互助协会官网](https://itxia.club/service)进行预约, 会有热情的IT侠学长学姐同学们帮你免费解决这个问题!

### 2. 配置C语言环境

这里给出本课程推荐的两款编程平台的教程: 

(TODO: Jetbrains 学生认证教程 + Toolbox安装 CLion (全平台通用))

[Windows 下配置 VS Code & CLion 的C语言环境教程 (2022年录制)](https://www.bilibili.com/video/BV1eP411j7Gw)

[~~Windows 下配置 VS Code 的C语言环境教程~~ (2021年录制, 不需要观看)](https://www.bilibili.com/video/BV1yA411F7Wk)

[~~Windows 下配置 CLion 的C语言环境教程~~ (2021年录制, 不需要观看)](https://www.bilibili.com/video/BV1GP4y1x7EH)

[~~Windows 下配置 Dev-C++ 的C语言环境教程~~ (2021年录制, 不需要观看)](https://www.bilibili.com/video/BV1sP4y1p7n5)

## **macOS**

苹果笔记本, 对于大学生活来说, 可能会带来不少麻烦 (比如软件不兼容, 没法打游戏等等). 但对于写代码来说, 也不失为一种很好的环境!

?> **"前途是光明的, 道路是曲折的."** 

### 配置C语言环境

(TODO: 配环境教程, Jetbrains 认证 + Toolbox 安装 CLion 全平台通用)

[macOS 下配置 CLion 的C语言环境教程 (2021年录制)](https://www.bilibili.com/video/BV1o44y117Zt)

## **Linux**

如果你在上大学前已经用起了 Linux 系统, 那你一定很会折腾电脑, 想必这里不用我多说, 但还是建议你仔细阅读完整篇文档. 

在大一上, 软件工作专业也会开设 *Linux 系统基础* 这门选修课, 各位同学可以在这门课上学到一些 Linux 系统的知识与操作.

### 配置C语言环境

(TODO: 配环境教程, Jetbrains 认证 + Toolbox 安装 CLion 全平台通用)

[Linux 下配置 VS Code 的C语言环境教程 (2021年录制)](https://www.bilibili.com/video/BV1L34y1Q74x)

[Linux 下配置 CLion 的C语言环境教程 (2021年录制)](https://www.bilibili.com/video/BV1Z64y1h7Jh)

<!-- tabs:end -->

## 验证你的C语言环境

当你能成功**运行**以下代码, 并输出 `Hello, world!` 时, **你就成功了!** :tada:

(VS Code 与 CLion 等不同编程平台运行代码的方式并不相同, 详情见上述视频与下述文档)

```c
#include <stdio.h>

int main() {
    printf("Hello, world!\n");
    return 0;
}
```

## 为你的编程平台锦上添花

(TODO: VS Code 与 CLion 的各种好用插件推荐, 快捷键, 自定义主题)

## 小结

到此为止, 你已经完成了本课程**最最重要的前置任务**, 先为自己**鼓个掌**! :clap:

不知道跟着教程配环境有没有让你体会到动手实践的**乐趣**, 但在以后的学习生活中(不止本课程), 你还会有**数不清的动手实践**要去做. 尽量让自己以折腾为乐, 乐在其中吧!
