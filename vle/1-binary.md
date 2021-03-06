## 01 | 二进制：不了解计算机的源头，你学什么编程

####一. 什么是二进制
十进制计数是使用 10 作为基数，那么二进制就是使用 2 作为基数，类比过来，二进制的数位就是 2^n 的形式

## 十进制转为二进制
js实现方式：用toString可以实现
```
const originNum = 123 
console.log(originNum.toString(2))  // "1111011"
const floatNumber = 879.765
console.log(floatNumber.toString(2))
```
## 二进制整数部分转换为十进制
直接使用parseInt(string, radix)

parseInt()可解析一个字符串，并返回一个整数
```let intNum=parseInt(800.029) // 800```

parseInt(string, radix)
string： 必需。要被解析的字符串
radix ： 可选。表示要解析的数字的基数
radix：该值介于 2 ~ 36 之间。如果省略该参数或其值为 0，则数字将以 10 为基础来解析。如果它以 “0x” 或 “0X” 开头，将以 16 为基数。如果该参数小于 2 或者大于 36，则 parseInt() 将返回 NaN
```
parseInt(800.029,0) // 800
parseInt(800.029,1) // NaN
parseInt(800.029,2) // NaN
```

####二. 计算机为什么使用二进制？

组成计算机系统的逻辑电路通常只有两个状态，即开关的接通与断开。断开的状态我们用“0”来表示，接通的状态用“1”来表示。由于每位数据只有断开与接通两种状态，所以即便系统受到一定程度的干扰时，它仍然能够可靠地分辨出数字是“0”还是“1”。因此，在具体的系统实现中，二进制的数据表达具有抗干扰能力强、可靠性高的优点。

#### 向左移位
二进制 110101 向左移一位，就是在末尾添加一位 0，因此 110101 就变成了 1101010。请注意，这里讨论的是数字没有溢出的情况
所谓数字溢出，就是二进制数的位数超过了系统所指定的位数。目前主流的系统都支持至少 32 位的整型数字，而 1101010 远未超过 32 位，所以不会溢出。如果进行左移操作的二进制已经超出了 32 位，左移后数字就会溢出，需要将溢出的位数去除

#### 向右移位
二进制 110101 向右移一位，就是去除末尾的那一位，因此 110101 就变成了 11010（最前面的 0 可以省略）。我们将 11010 换算为十进制，就是 26，正好是 53 除以 2 的整数商。所以二进制右移一位，就是将数字除以 2 并求整数商的操作

```
function leftShift(num: number, m: number) { // 左移
    return num << m;
}

function rightShift(num: number, m: number) { // 右移
    return num >>> m;
}

console.log(leftShift(53, 1)); // 106
console.log(rightShift(53, 1)); // 26
```
