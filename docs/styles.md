# 代码风格

<small>最后更新于 {docsify-updated}。</small>

?> 本文档将随着课程进度不断完善。

## 参考资料

- [Google C++ Style Guide](https://google.github.io/styleguide/cppguide.html)

- TODO: 华为代码风格手册？

## 工具

- TODO: sonarlint

- TODO: actions on save


## 代码风格守则

?> 基本原则：**代码首先是写给人看的!**

良好的代码风格与编程习惯能让你在 **Debug**（指减少或消除程序的漏洞与错误，尤其是在编写较大规模的项目代码时）或者**复习代码**时获得极佳的体验，即使有一定编码基础的同学也可以学习蚂蚁老师**课上展示**的**有一种美的简约的**代码风格。

### 变量命名法

良好的变量命名规范可以让阅读代码的人轻松地读懂代码的含义，一般来说程序员应该**让变量的名称与其意义相对应**，例如张三的名字这个变量的名称应该用 `name` 而不是 `abc`，虽然如何命名对编译器来说没有区别，但按前者的方式能极大地改善读者的体验！

#### 蛇形命名法

也被直观地成为下划线命名法，即用下划线将变量名的各个单词隔开，如 `my_name`，`total_number`。

#### 驼峰命名法

将各个单词首字母大写来隔开彼此的命名方法，又分为大驼峰命名法（如 `MyName`、`AntsOnlineCourse`）和小驼峰命名法（如 `myName`、`antsNumber`），大驼峰多用于`对象`，小驼峰多用于`变量`与`函数`。

?> 本课程中大家将主要接触**小驼峰**和**蛇形**命名法，用于命名变量和函数，但请**不要**在同一个程序中**同时出现多种**命名法！

#### ~~省时间命名法~~

**并没有这种命名法**，只是在一些**特定场合**（要求在短时间内写出代码，不需要后期复习和维护，编码者能在这段时间内清楚地记得变量名含义，不会给 debug 增加困难），如比赛和上机考试时临场使用。 但为了促进大家养成良好的习惯，建议大家在这类场合中也使用上述的变量命名方法。

强烈建议不要为了图省事就一味地使用 `a`、`b`、`c`、`m`、`n`、`x`、`y`、`z`… 这样的变量名。（除非题目上就是这样给你的）

正常写代码时，哪怕你取名为 `num`（为 `number` 的缩写）也比单字母好太多！ <small>(若给循环指示变量取 `i`、`j` 等单字母变量名，可以原谅，这是**约定俗成**的)</small>

### 代码注释

良好的注释可以帮助编码者在**维护和学习**时**快速掌握**相应代码段的**功能目的**。

请**杜绝**以下情况的发生:

>当我写下这一行代码时，只有我和上帝知道是什么意思。
>
>一个月后，只有上帝才知道是什么意思了……

### 大括号

C语言中当条件或循环分支中**只有一条语句时**可以省略大括号，但对于规范的代码风格来说，我们**不建议这样做**。

### 空白符

空白符，包括`空格`，`制表符`以及`换行符`。

我们强烈建议大家学习蚂蚁老师，在可以留空格的地方留上空格优化阅读体验，**爱护助教的眼睛**！ 如果懒得手输空格的话，请务必开启 IDE 的`保存时自动格式化`功能。

关于制表符则因人而异，我们建议大家在编码时**严格控制缩进**以优化阅读体验，而控制缩进的方法你既可以选择制表符也可以选择敲击固定数目的空格（蚂蚁老师推荐后者）。

在**不同功能的代码块**之间留出**一两个空行**可以帮助读者理解代码，同时也为你腾出了**写注释**的空间！