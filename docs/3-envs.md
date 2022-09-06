# C 语言开发环境

?> **此为本课程最重要的前置任务, 请务必在第一次课 (2022年9月23日) 之前完成 !!!**

## 选择 IDE

**IDE** ("Integrated Development Environment", 意为"集成开发环境")
就是集代码编辑器、编译器、调试器和图形用户界面等为一体的开发环境。

### 推荐 IDE

[![CLion LOGO](.assets/images/Clion.svg ':size=32') **CLion**](https://www.jetbrains.com/clion/) (由 Jetbrains 开发, 多平台使用)

[![VS Code LOGO](.assets/images/Visual_Studio_Code_1.35_icon.svg ':size=32') **Visual Studio Code**](https://code.visualstudio.com/) (简称 "VS Code", 由 Microsoft 开发，轻量级编辑器，可以插件方式配置成 C 语言开发环境)

?> 课堂讲解与演示将使用 CLion。(具体而言，是使用 Linux 系统 + CLion + Vim 插件。)

### 不推荐 IDE

- Xcode：由 Apple Inc 开发的 macOS 专属 IDE

- Dev-C++：很古老的 IDE, 功能不够全但足够应付本课程；界面不美观，严重影响工作心情

- Visual Studio 20xx：简称 "VS", 由 Microsoft 开发, 与上文的 VS Code 截然不同, 切勿混淆

- Vim：需经过复杂配置、长期训练，才能游刃有余，对初学者极不友好

?> 作为一名(准)程序员，[Vim](https://oi-wiki.org/tools/editor/vim/) 本身非常值得学习
(<small>蚂蚁老师课上会使用一些简单的 Vim 操作手法</small>)。

- Sublime、Notepad++、记事本、~~Microsoft Office Word~~、纸笔：通常只有找工作面试时才会用到

## 选择操作系统

<!-- tabs:start -->

## **Windows**

我们以 `Windows 11` 系统作演示, 也适用于其它 Windows 系统
(助教不负责解决 [![win98](.assets/images/win98.png ':size=50')](https://winworldpc.com/product/windows-98/98-second-edition) 带来的安装问题)。

### 1. 更换英文用户目录名 <!-- {docsify-ignore} -->

(TODO: 强调不能中文用户目录名, 查看用户目录名的方法)

!> **请先务必确保电脑的用户目录名为英文!**

请按照以下教程进行操作：
[Windows 更改用户名文字教程 (2022年编写整理；IT 侠互助协会)](https://www.yuque.com/itxia/help/change_win_account_name)

也可以在 [南京大学IT侠互助协会官网](https://itxia.club/service) 预约无偿支持服务。

感谢 IT 侠。

### 2. 配置 C 语言开发环境 <!-- {docsify-ignore} -->

[Jetbrains 学生认证 + Toolbox 安装 CLion (2022 年录制, 全平台通用)](https://www.bilibili.com/video/BV1Bd4y1G7a1)

[Windows + VS Code & CLion (2022 年录制)](https://www.bilibili.com/video/BV1eP411j7Gw)

[~~Windows + VS Code~~ (2021 年录制, 不需要观看)](https://www.bilibili.com/video/BV1yA411F7Wk)

[~~Windows + CLion~~ (2021 年录制, 不需要观看)](https://www.bilibili.com/video/BV1GP4y1x7EH)

[~~Windows + Dev-C++~~ (2021 年录制, 不需要观看)](https://www.bilibili.com/video/BV1sP4y1p7n5)

## **Linux**

### 配置C语言环境 <!-- {docsify-ignore} -->

[Jetbrains 学生认证 + Toolbox 安装 CLion (2022年录制, 全平台通用)](https://www.bilibili.com/video/BV1Bd4y1G7a1)

[Linux + CLion (2021年录制)](https://www.bilibili.com/video/BV1Z64y1h7Jh)

[Linux + VS Code (2021年录制)](https://www.bilibili.com/video/BV1L34y1Q74x)

?> 大一上学期, 软件工程专业会开设“Linux 系统基础”选修课。
大家可以从中学习 Linux 基本操作与系统知识。
CPL 课程并不要求 Linux 相关前置知识。

## **macOS**

### 配置 C 语言开发环境 <!-- {docsify-ignore} -->

[Jetbrains 学生认证 + Toolbox 安装 CLion (2022年录制, 全平台通用)](https://www.bilibili.com/video/BV1Bd4y1G7a1)

[macOS + CLion (2021年录制)](https://www.bilibili.com/video/BV1o44y117Zt)


<!-- tabs:end -->

## 验证 C 语言开发环境

当你能成功运行以下代码, 并输出 `Hello, world!` 时, 你就成功了! :tada:

(关于如何运行该代码，详见上述视频)

```c
#include <stdio.h>

int main() {
    printf("Hello, world!\n");
    return 0;
}
```

## 为开发环境锦上添花

(TODO: VS Code 与 CLion 的各种好用插件推荐, 快捷键, 自定义主题)

## 小结

到此为止, 你已经完成了本课程**最最重要的前置任务**, 先为自己鼓个掌! :clap:

作为一名(准)程序员，配置各种环境是必备技能。

繁琐的过程、不断的预期落空，难免会带来沮丧。

但动手自有动手的乐趣，生命不息，折腾不止，乐在其中吧。