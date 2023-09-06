# C 语言开发环境

?> **此为本课程最重要的前置任务，请务必在第一次课之前完成 ！！！** </br>
（软件学院为2023年9月15日，建雄书院为2023年9月12日）

<small>最后更新于 {docsify-updated}。</small>

## 选择 IDE

?> 若遇到无法下载问题，可查看 [软件资源](resources?id=软件资源)。</br>
高效使用各种 IDE，可查看 [cheat-sheets](https://github.com/hengxin/cheat-sheets) ([CLion](https://github.com/hengxin/cheat-sheets/tree/master/jetbrains), [VSCode](https://github.com/hengxin/cheat-sheets/tree/master/vscode))。

**IDE** ("Integrated Development Environment"，意为"集成开发环境")

就是集代码编辑器、编译器、调试器和图形用户界面等为一体的开发环境。

### 推荐 IDE

[![CLion LOGO](.assets/images/Clion.svg ':size=32') **CLion**](https://www.jetbrains.com/clion/)：由 Jetbrains 开发，Windows / macOS / Linux 系统下均可使用，需申请 Jetbrains 学生认证。

[![VS Code LOGO](.assets/images/Visual_Studio_Code_1.35_icon.svg ':size=32') **Visual Studio Code**](https://code.visualstudio.com/)：简称 "VS Code"，由 Microsoft 开发，轻量级编辑器，Windows / macOS / Linux 系统下均可使用，可以插件方式配置成 C 语言开发环境。

?> 软件学院的课堂讲解与演示将使用 CLion（Linux 系统 + CLion IDE + Vim 插件）。</br>
（任意系统下）使用 CLion 会更加容易跟上课堂节奏，若要安装上述两款 IDE，请仔细观看[教程视频](envs?id=选择操作系统)。

### 不作推荐的 IDE

若安装以下 IDE，本课程的 [助教团队](qa?id=助教团队) 可能无法提供答疑帮助。

- Visual Studio 20xx：简称 "VS"，由 Microsoft 开发，与上文的 VS Code 截然不同，切勿混淆，仅在 Windows 系统下有完善的支持；由于其自带的编译器与测试平台并不相同，代码与行为的不一致可能产生一些误解，造成一些麻烦，导致平时编程练习无法顺利完成。

- Dev-C++：很古老的 IDE，功能不够全但足够应付本课程；界面不美观，严重影响工作心情。

- Xcode：由 Apple Inc 开发的 macOS 专属 IDE；由于助教团队均未熟练使用过，可能无法解决其产生的问题。

- Sublime：轻量级编辑器，需经过插件配置成 C 语言开发环境。

- Notepad++、记事本、~~Microsoft Office Word~~、纸笔：通常只有找工作面试时才会用到。

- Vim：需经过复杂配置、长期训练，才能游刃有余，对初学者极不友好。

?> 作为一名(准)程序员，[Vim](https://oi-wiki.org/tools/editor/vim/) 本身非常值得学习。</br>
<small>（蚂蚁老师课上会使用一些简单的 Vim 操作手法）</small>

## 选择操作系统

<!-- tabs:start -->

## **Windows**

我们以 `Windows 11` 系统作演示，也适用于其它 Windows 系统。

（助教解决不了 ![Windows Logo 95](.assets/images/Windows_Logo_(1992-2001).svg ':size=50') 之前版本带来的安装问题）

### 1. 更换英文用户目录名 <!-- {docsify-ignore} -->

如果 `C:\Users` 目录下的 `用户目录名` 为中文，将会导致 无法安装部分软件、配置环境失败 等一系列不可控问题，带来许多麻烦。

!> **请先务必确保电脑的用户目录名为英文或数字！**

若为中文，请按照以下教程进行操作：

[Windows 更改用户名文字教程 (2022年编写整理；IT 侠互助协会)](https://www.yuque.com/itxia/help/change_win_account_name)

也可以在 [南京大学IT侠互助协会官网](https://itxia.club/service) 预约寻求无偿支持服务。

感谢 IT 侠们。

### 2. 配置 C 语言开发环境 <!-- {docsify-ignore} -->

[Jetbrains 学生认证 + Toolbox 安装 CLion (2022 年录制，全平台通用)](https://www.bilibili.com/video/BV1Bd4y1G7a1)

[Windows + VS Code & CLion (2022 年录制，CLion 部分可以看👆)](https://www.bilibili.com/video/BV1eP411j7Gw)

[~~Windows + VS Code~~ (2021 年录制，不需要观看)](https://www.bilibili.com/video/BV1yA411F7Wk)

[~~Windows + CLion~~ (2021 年录制，不需要观看)](https://www.bilibili.com/video/BV1GP4y1x7EH)

[~~Windows + Dev-C++~~ (2021 年录制，不需要观看)](https://www.bilibili.com/video/BV1sP4y1p7n5)

## **Linux**

### 配置C语言环境 <!-- {docsify-ignore} -->

[Jetbrains 学生认证 + Toolbox 安装 CLion (2022年录制，全平台通用)](https://www.bilibili.com/video/BV1Bd4y1G7a1)

[Linux + CLion (2021年录制)](https://www.bilibili.com/video/BV1Z64y1h7Jh)

[Linux + VS Code (2021年录制)](https://www.bilibili.com/video/BV1L34y1Q74x)

?> 大一上学期，软件学院会开设“Linux 系统基础”选修课。</br>
大家可以从中学习 Linux 基本操作与系统知识。</br>
本课程并不要求 Linux 相关前置知识。技术科学试验班同学若感兴趣，可以自学。

## **macOS**

### 配置 C 语言开发环境 <!-- {docsify-ignore} -->

[Jetbrains 学生认证 + Toolbox 安装 CLion (2022年录制，全平台通用)](https://www.bilibili.com/video/BV1Bd4y1G7a1)

[macOS + CLion (2021年录制)](https://www.bilibili.com/video/BV1o44y117Zt)

<!-- tabs:end -->

## 验证 C 语言开发环境

当你能成功运行以下代码，并输出 `Hello, world!` 时，你就成功了！ :tada:

（关于如何运行该代码，详见上述视频）

```c
#include <stdio.h>

int main() {
    printf("Hello, world!\n");
    return 0;
}
```

## 为开发环境锦上添花--插件推荐

- CLion
  - Indent Rainbow：彩虹缩进

  - Rainbow Brackets：彩虹括号

  - [SonarLint](https://www.sonarlint.org/index.html): 代码检查工具

  - Key Promoter X：快捷键提示

  - WakaTime：统计写代码的时间

  - IdeaVim：在 CLion 使用 Vim，如果你还不会 Vim，请先不要启用，否则会导致无法输入的问题

- VS Code
  - C/C++ Extension Pack：C 语言扩展包

  - Code Runner：一键编译运行代码

  - indent-rainbow：彩虹缩进

  - GitLens、Git History、Git Graph：Git GUI 扩展包

  - Vim：在 VS Code 使用 Vim，如果你还不会 Vim，请先不要启用，否则会导致无法输入的问题

?> 扩展商店里还有许多好玩好用的扩展等着你去探索!

## 小结

到此为止，你已经完成了本课程**最最重要的前置任务**，先为自己鼓个掌！ :clap:

作为一名(准)程序员，配置各种环境是必备技能。

繁琐的过程、不断的预期落空，难免会带来沮丧。

但动手自有动手的乐趣，生命不息，折腾不止，乐在其中吧！