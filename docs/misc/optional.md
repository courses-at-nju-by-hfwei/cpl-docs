# 选做题思路略讲

<small>最后更新于 {docsify-updated}。</small>

?> 选做题不同于平时的作业题，需要你有更强的<br>- 测试样例构造能力。在合法的输入中找出尽可能多的 Corner-Case，全面地测试你的代码<br>- 代码组织能力。编写出可读、结构清晰、函数功能明确的代码，会让你的 debug 更加熟练

不要妄想样例对了就能对（这点对于平时作业也是一样）。因为最终的测试用例会是顶级规模。

先写对了，再优化。

> Premature optimization is the root of all evil.  --Knuth



## E 超级计算器

首先有一个数据类型来保存超长数字。然后是对数据类型的操作。

```c
typedef struct BigInt_ {
    int area[1200];
    // int 的上限是 2147483647。考虑到加减法进退位，我们使用其中的 9 个十进制位
    // 那么 1200 个 int 足够放了。area[0] 为最低的 9 位
} BigInt;  // 给结构体起个别名

// 明确要实现的四个函数。参数类型直接为结构体，返回类型也一样。
BigInt add(BigInt a, BigInt b);
BigInt sub(BigInt a, BigInt b);
BigInt mul(BigInt a, BigInt b);
BigInt idiv(BigInt a, BigInt b);   // div 与 stdlib.h 冲突

// 读入，输出数字
BigInt readBigInt();
void writeBigInt(BigInt bigInt);
```

有了如上的实现，主函数的结构很明确

```c
while (n--) {
	BigInt a = readBigInt();
    // TODO(): get operator op
    BigInt b = readBigInt();
    switch(op) {
        case '+': writeBigInt(add(a, b)); break;
        case '-': ...
        ...
        default: assert(0);   // what is assert? STFW
    }
}
```



`add()` `sub()`，easy，处理好进退位即可。

`mul()` 使用 [快速幂 - OI Wiki (oi-wiki.org)](https://oi-wiki.org/math/binary-exponentiation/)。**先看一看这篇！学习原理很重要！**

```c
// int 的快速幂乘法
int mul(int a, int b) {
    int ret = 0;
    while (a != 0) {
        if (a & 1) ret += b;
        a = a >> 1;  // 与 a = a / 2 结果等价
        b = b + b;  // 与 b = 2 * b 结果等价
    }
    return ret;
}
```

应用到 `BigInt` 上，请实现：

- `BigInt` 右移一位 / 除以 2
- 判断某个`BigInt` 不等于 0



`idiv()` 和快速幂相似的思路。想不出来可以参考 [LeetCode29 Medium 不用除号实现除法 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/108566985)



FAQ

- 为什么不用指针？
  - 没必要。`struct` 类型传参、赋值、返回值在 C 语言中是明确定义的行为。使用指针分配内存带来的管理操作会对扰乱代码思路，产生额外的负担。
- 网上有很多高精度计算的算法。你为什么推荐这样写？
  - 比起那点性能损失，代码的可维护性是首要的。大多高精度算法用极其难读的写法换到了一些性能优势，但本题数据规模不大，那点优化显得没有必要。你的代码优化到什么程度，取决于需求。采取比较易读的写法，调起 Bug 来也得心应手，对某个函数功能进行单元测试也非常容易。

<!-- tabs:start -->

### **Tilnel**

我自己觉得比出题人代码容易看懂一点。

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <stdbool.h>
#include <math.h>

typedef struct _BigInt {
    int bit[1200];
} BigInt;

BigInt zero = {};
BigInt one = (BigInt){ .bit[0] = 1 };

BigInt readBigInt() {
    BigInt bigInt = zero;
    char buf[10005];
    scanf("%s", buf);
    int len = strlen(buf);
    for (int i = 0; i < len; i++) {
        bigInt.bit[i / 9] += (buf[len - 1 - i] - '0') * pow(10, i % 9);
    }
    return bigInt;
}

void writeBigInt(BigInt bigInt) {
    int i;
    for (i = 1199; i > 0; i--) {
        if (bigInt.bit[i] != 0) break;
    }
    printf("%d", bigInt.bit[i]);
    for (i--; i >= 0; i--) {
        printf("%09d", bigInt.bit[i]);
    }
    putchar('\n');
}

BigInt add(BigInt a, BigInt b) {
    BigInt sum = zero;
    int carry = 0;
    for (int i = 0; i < 1200; i++) {
        int tmp = a.bit[i] + b.bit[i] + carry;
        carry = tmp / 1000000000;
        sum.bit[i] = tmp - 1000000000 * carry;
    }
    return sum;
}

BigInt sub(BigInt a, BigInt b) {
    BigInt diff = zero;
    int carry = 0;
    for (int i = 0; i < 1200; i++) {
        int tmp = a.bit[i] - b.bit[i] - carry;
        carry = tmp < 0 ? 1 : 0;
        diff.bit[i] = tmp + 1000000000 * carry;
    }
    return diff;
}

BigInt div2(BigInt a) {
    BigInt ret = zero;
    int carry = 0;
    for (int i = 24; i >= 0; i--) {
        int old_carry = carry;
        carry = a.bit[i] & 1;
        ret.bit[i] = (a.bit[i] + 1000000000 * old_carry) / 2;
    }
    return ret;
}

bool geq(BigInt a, BigInt b) {
    for (int i = 24; i >= 0; i--) {
        if (a.bit[i] == b.bit[i]) continue;
        if (a.bit[i] > b.bit[i]) return true;
        else return false;
    }
    return true;
}

bool eq(BigInt a, BigInt b) {
    for (int i = 24; i >= 0; i--) {
        if (a.bit[i] != b.bit[i]) return false;
    }
    return true;
}


BigInt mul(BigInt a, BigInt b) {
    BigInt prod = zero;
    while (!eq(a, zero)) {
        if (a.bit[0] & 1) {
            prod = add(prod, b);
        }
        b = add(b, b);
        a = div2(a);
    }
    return prod;
}

BigInt idiv(BigInt a, BigInt b) {
    BigInt quot = zero;
    BigInt pow = b;
    BigInt pow2 = one;
    int cnt = 0;
    while (geq(a, pow)) {
        cnt++;
        pow = add(pow, pow);
        pow2 = add(pow2, pow2);
    }
    while (cnt--) {
        pow = div2(pow);
        pow2 = div2(pow2);
        if (geq(a, pow)) {
            quot = add(quot, pow2);
            a = sub(a, pow);
        }
    }
    return quot;
}

int main() {
    int n;
    char op;
    scanf("%d", &n);
    while (n--) {
        BigInt a, b, c;
        c = zero;
        a = readBigInt();
        scanf(" %c", &op);
        b = readBigInt();
        switch (op) {
            case '+': c = add(a, b); break;
            case '-': c = sub(a, b); break;
            case '*': c = mul(a, b); break;
            case '/': c = idiv(a, b); break;
            default: break;
        }
        writeBigInt(c);
    }
    return 0;
}
```

### **Labelray**

```c
#include <stdio.h>
#include <string.h>

int main() {
    int T, l;
    char sa[10010], sb[10010], op[2];
    int a[10010], b[10010], c[10010], d[10010];
    scanf("%d", &T);
    while(T--) {
        scanf("%s%s%s", sa + 1, op, sb + 1);
        int la = strlen(sa + 1);
        int lb = strlen(sb + 1);
        for (int i = 1; i <= 10000; i++)
            a[i] = b[i] = c[i] = 0;
        for (int i = 1; i <= la; i++) 
            a[i] = sa[la - i + 1] - '0';
        for (int i = 1; i <= lb; i++)
            b[i] = sb[lb - i + 1] - '0';
        switch (op[0]) {
            case '+':
                l = la > lb ? la : lb;
                for (int i = 1; i <= l; i++) {
                    c[i] += a[i] + b[i];
                    if (c[i] > 9) {
                        c[i] -= 10;
                        c[i + 1] += 1;
                    }
                }
                if (c[l + 1] > 0)
                    l += 1;
                for (int i = l; i > 0; i--)
                    printf("%d", c[i]);
                putchar('\n');
                break;
            case '-':
                l = la > lb ? la : lb;
                for (int i = 1; i <= l; i++) {
                    c[i] += a[i] - b[i];
                    if (c[i] < 0) {
                        c[i] += 10;
                        c[i + 1] -= 1;
                    }
                }
                while(l > 1 && c[l] == 0) l--;
                for (int i = l; i > 0; i--)
                    printf("%d", c[i]);
                putchar('\n');
                break;
            case '*':
                for (int i = 0; i < lb; i++) {
                    for (int j = 0; j <= la + 1; j++)
                        d[j] = 0;
                    for (int j = 1; j <= la; j++) {
                        d[j] += a[j] * b[i + 1];
                        if (d[j] > 9) {
                            d[j + 1] += d[j] / 10;
                            d[j] %= 10;
                        }
                    }
                    for (int j = 1; j <= la + 1; j++) {
                        c[i + j] += d[j];
                        if (c[i + j] > 9) {
                            c[i + j + 1] += c[i + j] / 10;
                            c[i + j] %= 10;
                        }
                    }
                }
                l = la + lb;
                while (l > 1 && c[l] == 0) l--; 
                for (int i = l; i > 0; i--)
                    printf("%d", c[i]);
                putchar('\n');
                break;
            case '/':
                for (int i = la; i - lb >= 0; i--) {
                    while(1) {
                        int fl = 1;
                        for (int j = 0; a[i+1] == 0 && j < lb; j++) {
                            if (a[i - j] > b[lb - j]) 
                                break;
                            else if (a[i - j] < b[lb - j]) {
                                fl = 0;
                                break;
                            }
                        }
                        if (fl == 0)
                            break;
                        for (int j = lb - 1; j >= 0; j--) {
                            a[i - j] -= b[lb - j];
                            if (a[i - j] < 0) {
                                a[i - j] += 10;
                                a[i - j + 1] -= 1;
                            } 
                        }
                        c[i - lb + 1] += 1;
                    }
                }
                l = la;
                while (l > 1 && c[l] == 0) l--;
                for (int i = l; i > 0; i--) {
                    printf("%d", c[i]);
                }
                putchar('\n');
                break;
        }
    }
    return 0;
}
```
### **Sakiyary**

我觉得我的版本才是最清晰的！

````c
#include <stdbool.h>
#include <stdio.h>
#include <string.h>

char a[10005], b[10005], op;
int c[10005], d[10005], e[10005], alen, blen, clen, i, j;

void Plus() {
    clen = (alen > blen ? alen : blen) + 1;
    for (i = 0; i < clen - 1; i++) {
        c[i] += d[i] + e[i];
        if (c[i] >= 10) {
            c[i + 1] += 1;
            c[i] -= 10;
        }
    }
}

void Minus() {
    clen = alen;
    for (i = 0; i < clen; i++) {
        c[i] += d[i] - e[i];
        if (c[i] < 0) {
            c[i + 1] -= 1;
            c[i] += 10;
        }
    }
}

void Multiply() {
    clen = alen + blen;
    for (i = 0; i < clen; i++) {
        for (j = 0; j <= i; j++)
            c[i] += d[j] * e[i - j];
        if (c[i] >= 10) {
            c[i + 1] += c[i] / 10;
            c[i] %= 10;
        }
    }
}

bool Equal(int d[], int e[], int i) {
    if (d[i + blen] != 0)
        return true;
    for (j = blen - 1; j >= 0; j--) {
        if (d[i + j] > e[j])
            return true;
        if (d[i + j] < e[j])
            return false;
    }
    return true;
}

void Divide() {
    clen = alen - blen + 1;
    for (i = clen - 1; i >= 0; i--)
        while (Equal(d, e, i)) {
            for (j = 0; j < blen; j++) {
                d[i + j] -= e[j];
                if (d[i + j] < 0) {
                    d[i + j] += 10;
                    d[i + j + 1]--;
                }
            }
            c[i]++;
        }
}

int main() {
    int n;
    scanf("%d\n", &n);
    for (int m = 0; m < n; m++) {
        scanf("%s %c %s", a, &op, b);
        alen = strlen(a);
        blen = strlen(b);
        for (i = 0; i < alen; i++)
            d[alen - i - 1] = a[i] - '0';
        for (i = 0; i < blen; i++)
            e[blen - i - 1] = b[i] - '0';
        switch (op) {
            case '+':
                Plus();
                break;
            case '-':
                Minus();
                break;
            case '*':
                Multiply();
                break;
            case '/':
                Divide();
                break;
            default:
                break;
        }
        for (i = clen; i > 0; i--)
            if (c[i] != 0)
                break;
        for (; i >= 0; i--)
            printf("%d", c[i]);
        printf("\n");
        memset(c, 0, sizeof c);
        memset(d, 0, sizeof d);
        memset(e, 0, sizeof e);
    }
    return 0;
}
```

<!-- tabs:end -->
