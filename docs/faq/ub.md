# Undefined Behaviors (UB)

<small>最后更新于 {docsify-updated}。</small>

?> [Undefined behavior @ cppreference.com](https://en.cppreference.com/w/cpp/language/ub)、[A Guide to Undefined Behavior in C and C++ (Part 1/2/3)](https://blog.regehr.org/archives/213) 与 [Undefined behavior @ wiki](https://en.wikipedia.org/wiki/Undefined_behavior)
总结了 C/C++ 中各类 Undefined Behaviors (UB)，并讨论了 UB 带来的好处与风险。</br>
**本页面按照课程进度总结学生将会遇到的各类 UBs。**

!> 代码中应避免出现任何 UBs!

## 什么是“未定义行为”?

“未定义行为”是 ……。

## `scanf/printf` 中类型不匹配
### 描述
### 示例

## 整数除 0
### 描述
### 示例

## 访问未初始化的局部变量
### 描述
### 示例

## 数组访问越界
### 描述
### 示例

## 表达式求值顺序
### 描述
### 示例

`++i + i++`

## 其它参考资料
- [What Every C Programmer Should Know About Undefined Behavior #1/3](https://blog.llvm.org/2011/05/what-every-c-programmer-should-know.html)
- [Undefined Behavior and Fermat’s Last Theorem](https://web.archive.org/web/20201108094235/https://kukuruku.co/post/undefined-behavior-and-fermats-last-theorem/)
- [Undefined behavior can result in time travel (among other things, but time travel is the funkiest)](https://devblogs.microsoft.com/oldnewthing/20140627-00/?p=633)