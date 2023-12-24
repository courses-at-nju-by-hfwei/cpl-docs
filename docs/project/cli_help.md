# 命令行交互简易教程

<small>最后更新于 {docsify-updated}。</small>

?> 代码为主，用注释解释，非常简要。
## Windows 篇

!> 请在 Windows 商店下载安装 [Windows Terminal](http://docs.cpl.icu/#/resources?id=%E6%95%99%E7%A8%8B%E8%A7%86%E9%A2%91) 来测试你的程序，以保证良好的体验。</br>系统 powershell 的自带蓝色界面有奇怪的特性。

原版贴士：
> Windows 双击编译好的 .exe 查看效果。一般来说，会弹出一个黑框。或者设置你的 IDE 运行程序时弹出 cmd。不要用 IDE 自带的小到不行的终端，对眼睛不好。如果你以获取的终端尺寸动态设置游戏界面尺寸，请不要用系统原生的 powershell gui 程序以及 CMD，因其可以滚动的特性，读到的窗口高度会是30000行，（系统原生CMD读到的会是9000行），也许不利于你绘制字符界面。可以使用windows terminal（微软应用商店可找到）

````c
#include <conio.h>  // 必须
#include <stdio.h>
#include <windows.h>   // 必须
HANDLE consoleHandle;  // 操作控制台（也就是那个黑框框）需要的一个变量
int w, h;              // 高度，宽度，对应 y 和 x
// 在屏幕上 y, x 的位置打印一个 ch
void mvaddch(int y, int x, char ch) {
    COORD co = (COORD){.X = x, .Y = y};
    SetConsoleCursorPosition(consoleHandle, co);  // 设置你的光标位置
    putchar(ch);                                  // 在这里打印一个字符
}
// 类似地，你可以以这种方式定义一些在某个位置打印字符串的函数
int main() {
    consoleHandle = GetStdHandle(STD_OUTPUT_HANDLE);   // 初始化这个操作器
    CONSOLE_SCREEN_BUFFER_INFO csbi;                   // 屏幕的信息
    GetConsoleScreenBufferInfo(consoleHandle, &csbi);  // 获取屏幕信息
    w = csbi.dwSize.X;
    h = csbi.dwSize.Y;  // 得到宽度高度
    // 游戏里面，如果一直有输入的光标，就有点不好看。我们可以让它不显示
    CONSOLE_CURSOR_INFO cci;  // 光标信息
    cci.dwSize = 100;
    cci.bVisible = FALSE;                       // 不可见
    SetConsoleCursorInfo(consoleHandle, &cci);  // 将光标特性应用到控制台
    // 到这里，闪烁的光标就消失了。
    while (1) {
        while (kbhit() != 0) {  // 如果它检测到有键盘敲击，返回非零。没有则返回 0
            // 有键盘敲击，我们获取是哪一个键
            char c = getch();
            mvaddch(h / 2, w / 2, c);  // 显示在屏幕中心
            Sleep(1000);               // 程序暂停 1000 毫秒
        }
    }
    // 游戏结束，我们要恢复光标显示
    cci.bVisible = TRUE;                        // 可见
    SetConsoleCursorInfo(consoleHandle, &cci);  // 重新设置
}

````
如果需要清屏，只需要在整个屏幕上填满空格。

## Linux 篇

我个人使用了 libncurses。

debian、ubuntu请： 

````bash
sudo apt install libncurses-dev
````

编译：

````bash
gcc a.c -lncurses
````

````c
#include <ncurses.h>  // 必须
#include <stdio.h>
#include <unistd.h>  // 必须
int w, h;            // 终端的宽度和高度
int main() {
    initscr();              // 初始化屏幕
    cbreak();               // 允许程序在你还没有回车的时候就读取你的输入
    nodelay(stdscr, true);  // 通常来说，在没有输入的时候，程序会等待你。
    // 设置该项后，将不再等待，没有输入就返回 EOF
    getmaxyx(stdscr, h, w);  // 获取窗口的字符高度和宽度
    noecho();                // 关闭回显。你输入的字符不会在窗口中显示。
    curs_set(false);         // 关闭光标显示
    while (1) {
        char ch;
        while ((ch = getch()) != EOF) {                            // 不等待地获取输入字符
            mvaddch(h / 2, w / 2, ch);                             // 在屏幕中间显示字符
            mvprintw(h / 2 + 1, w / 2 - 5, "Hello World %d", ch);  // 在坐标位置
            输出格式字符串
            refresh();        // 将你的改动真正输出到屏幕上。否则可能有延迟
            usleep(1000000);  // 暂停 1000000 微秒
            // 或 sleep(1); 暂停一秒
        }
    }
    clear();  // 清除屏幕
    // 恢复屏幕状态
    nocbreak();
    curs_set(true);
    echo();
    endwin();  // 结束屏幕交互
}
````