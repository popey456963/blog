---
layout: post
title:  "Number Bases"
date:   2016/02/24 15:52
categories: [Computing, A-Level, AQA]
permalink: /archive/number-bases
---

The number base of a number is the number of unique digits possible in that number. eg:

- Binary - Base-2 contains 2 digits: 1 and 0
- Hexadecimal - Base-16 contains 16 digits: 0-F
- Decimal - Base-10 contains 10 digits: 0-9
- Octal - Base-8 contains 8 digits: 0-7

#### **Counting in binary, decimal and hexadecimal**

In each number system, we count from 0 up to the maximum value in a single digit.
eg in decimal:

~~~
0
1
2
3
4
5
6
7
8
9
~~~

When we reach a maximum in one digit, we start a new column of digits and reset the first column.

~~~
                        .
                        .
                        .
                        8
                        9 - Max digit
Second column set to -  10
 one                    11
                        12
                        13
                        .
                        .
                        .
~~~

#### **Place values**
In decimal, the place values increase by a factor of 10 as new columns are added.

#### **Units of binary**
1 *bi*nary digi*t* = 1 bit
8 bits = 1 byte
4 bits = 1 nybble $$\gets$$ Joke unit
2 bits = crumb $$\gets$$ Joke unit

#### **Multiples of bytes and bits**

The unit multipliers of bits and bytes follow the S.I. convention:

- Kilo = 1,000 = k
- Mega = 1,000,000 = M
- Giga = 1,000,000,000 = G
- Terra = 1,000,000,000,000 = T
- Peta = 1,000,000,000,000,000 = P
- Exa = 1,000,000,000,000,000,000 = E
- Zetta = 1,000,000,000,000,000,000,000 = Z
- Yotta = 1,000,000,000,000,000,000,000,000 = Y

These prefixes are in common use but are not the best units to use for binary data. Becuase of this, we have **preferred units**:

- (ki) Kibi = $$1024$$ = $$2^1$$
- (Mi) Mebi = $$1024^2$$ = $$2^{20}$$
- (Gi) Gibi = $$1024^3$$ = $$2^{30}$$

#### **Bytes and hexadecimal**

1 byte is 2 nybbles.

Hexadecimal uses the digits 0-9 A-F to represent 16 different values. A binary nybble can contain 16 different values so it maps neatly to hexadecimal.

|Decimal|Hexadecimal|Binary|
|------:|----------:|-----:|
|0|0|0000|
|7|7|0111|
|12|C|1100|

##### **To convert hex to decimal**
`6f` to decimal
$$
6\times16^1+F\times16^0 = 6\times16+F\\
6\times16 + 15 = 111_{10}
$$

>**Note:**
>It is unlikely but **possible** that you might need to convert a multi-digit hex number to decimal.
>eg:
>$$
6\times16^2+F\times16^1+C\times16^0=1788_{10}
$$

#### **Number conversion exercises**

| Decimal | Hexadecimal | Binary |
|-:|-:|-:|
| 243 | F3 | 11110011 |
| 97 | 61 | 01100001 |
| 123 | 7B | 01111011 |
| 195 | C3 | 11000011 |
| 189 | BD | 10111101 |
| 251 | FB | 11111011 |
| 26 | 1A | 00011010 |
| 90 | 5A | 01011010 |

#### **More about binary numbers**

In $$1001 111$$, the first $$1$$ is the most significant bit (**MSB**), and the last $$1$$ is the least significant bit (**LSB**). This example is also an unsigned binary integer. This means that the kind of number this is is never specified.

> **Note**
> The type of binary number needs to be specified if you are using anything other than an unsigned binary integer, because pure binary numbers are ambiguous.

##### **Addition of unsigned binary integers**

$$
\begin{align}
&01101010& \\
&\underline{00101001}+&\\
&\underline{10010011}&\\
&^{1\,1\,\;\,1}&
\end{align}
$$
> **Overflow**
> If 2 numbers are added together and the sum is bigger than the spaaaaaace allocated, an overflow will occur.

##### **Multiplying unsigned binary integers**

eg:

$$
10111\\
\; \;\;\;\;\;\;\;\;\;11  \times \\
\overline{101110  }\;\;\\
\,\underline{10111} \\
1000101\;\;\;
$$

#### **Numbers with a fractional part**

Often, calculations produce numbers that have fractional parts, such as $$5\div3$$. The decimal system is very similar to the binary system.:
Decimal:

|$$100$$|$$10$$|$$1$$|$$.$$|$$\frac{1}{10}$$|$$\frac{1}{100}$$|
|-|-|-|-|-|-|
|$$2$$|$$5$$|$$6$$|$$.$$|$$7$$|$$1$$|

Binary:

|$$16$$|$$8$$|$$4$$|$$2$$|$$1$$|$$.$$|$$\frac{1}{2}$$|$$\frac{1}{4}$$|$$\frac{1}{8}$$|
|-|-|-|-|-|-|-|-|-|
|$$1$$|$$1$$|$$0$$|$$1$$|$$0$$|$$.$$|$$1$$|$$0$$|$$1$$|

>**Note**
>In the binary example, it was assumed that the 3 LSBs were the fractional part becuase in binary, there is no symbol for "$$.$$" and so the position of the "$$.$$" must be assumed. This assumption is known as **fixed point coding**.

We can also use 2's compliment with this fixed point coding.
eg:

|$$-16$$|$$8$$|$$4$$|$$2$$|$$1$$|$$.$$|$$\frac{1}{2}$$|$$\frac{1}{4}$$|$$\frac{1}{8}$$|
|-|-|-|-|-|-|-|-|-|
|$$1$$|$$1$$|$$0$$|$$1$$|$$0$$|$$.$$|$$1$$|$$0$$|$$1$$|

#### **Floating point form**

Often, scientific notation is used to write numbers. for example:
$$
A\times10^8
$$

A similar notation is used when 2's compliment is used to to represent signed numbers that range from small to large:  M$$\times$$Base$$^E$$

##### **Floating points in binary**

Floating point gets around the limitations of fixed point by using a format similar to scientific notation. eg:
$$
3.141\times10^3
$$

The "$$3.141$$" is known as the *Mantissa* and the "$$\times10^3$$" is known as the exponent. So say there was a 32 bit system, the mantissa would be 24 bits and the exponent would be 8 bits.

>**Recap of 2's compliment**
>If it is positive, convert to binary normally.
>If it is negative, convert to binary, invert the bits and add 1.

$$
\overset{\mathsf{Mantissa}}{\overset{-2^{0}}{0}\ \overset{•}{}\ \overset{2^{-1}}{1}\ \overset{2^{-2}}{1}\ \overset{2^{-3}}{0}\ \overset{2^{-4}}{1}\ \overset{2^{-5}}{0}}\ \ \ \ \ \ \ \ \overset{\mathsf{Exponent}}{\overset{-2^3}{0}\ \overset{2^2}{1}\ \overset{2^1}{0}\ \overset{2^0}{1}}
$$
This can be written as $$0.11010\times10^{0101}$$.
The exponent evaluates to $$+5_{10}$$
This means that the binary point is moved 5 places to the right:
$$
0.\overset{↷}{1}\overset{↷}{1}\overset{↷}{0}\overset{↷}{1}\overset{↷}{0}_2 = 011010.0_2 \mathsf{\ or\ just\ }011010_2
$$
Which evaluates to $$16 + 8 + 2 = 26_{10}$$

It is also easy to convert back:
You simply convert the decimal number to binary. You then work out how many places you need to move the binary point to move it to before the MSB. The "$$.$$" is implied after the MSB.

Negative mantissas can also be used:
$$
\overset{\mathsf{Mantissa}}{\overset{-2^{0}}{1}\ \overset{2^{-1}}{1}\ \overset{2^{-2}}{0}\ \overset{2^{-3}}{0}\ \overset{2^{-4}}{1}\ \overset{2^{-5}}{1}}\ \ \ \ \ \ \ \ \overset{\mathsf{Exponent}}{\overset{-2^3}{0}\ \overset{2^2}{0}\ \overset{2^1}{1}\ \overset{2^0}{1}}
$$
So the point is implied after the MSB:
$$
\overset{\mathsf{Mantissa}}{\overset{-2^{0}}{1}\ \overset{•}{}\ \overset{2^{-1}}{1}\ \overset{2^{-2}}{0}\ \overset{2^{-3}}{0}\ \overset{2^{-4}}{1}\ \overset{2^{-5}}{1}}\ \ \ \ \ \ \ \ \overset{\mathsf{Exponent}}{\overset{-2^3}{0}\ \overset{2^2}{0}\ \overset{2^1}{1}\ \overset{2^0}{1}}
$$
The exponent moves the binary point $$11_2$$ or $$3_{10}$$ positions to the right:
$$
\overset{\mathsf{Mantissa}}{\overset{-2^{3}}{1}\ \overset{2^{2}}{1}\ \overset{2^{1}}{0}\ \overset{2^{0}}{0}\ \overset{•}{}\ \overset{2^{-1}}{1}\ \overset{2^{-2}}{1}}\ \ \ \ \ \ \ \ \overset{\mathsf{Exponent}}{\overset{-2^3}{0}\ \overset{2^2}{0}\ \overset{2^1}{1}\ \overset{2^0}{1}}
$$
Which equates to $$1100.11_2$$ or $$-3.25_{10}$$

#### **Converting from unsigned decimal numbers to unsigned binary**

With integers this is easy:$$15_{10} \to 1111_2$$And with some decimal:
$$15.625_{10} \to 1111.101_2\ \ \ =\ \ \ .\overset{0.5}{1}\ \overset{0.25}{0}\ \overset{0.125}{0}$$But with others:
$$15.6_{10} \to 1111.1010\dots_2$$Which has to be rounded and when converted back $$\neq15.6$$.

>**Note**
>Converting decimal numbers to fixed point unsigned binary introduces errors.



#### **Research task**

**Find out how signed binary integers can be stored using 2's compliment.**

Two's complement is a clever way of storing integers so that common math problems are very simple to implement.

To understand, you have to think of the numbers in binary.

It basically says,

- for zero, use all 0's.
- for positive integers, start counting up, with a maximum of 2<sup>(number of bits - 1)</sup>-1.
- for negative integers, do exactly the same thing, but switch the role of 0's and 1's (so instead of starting with 0000, start with 1111 - that's the "complement" part).

Let's try it with a mini-byte of 4 bits (we'll call it a [nibble][1] - 1/2 a byte).

- `0000` - zero
- `0001` - one
- `0010` - two
- `0011` - three
- `0100` to `0111` - four to seven

That's as far as we can go in positives. 2<sup>3</sup>-1 = 7.

For negatives:

- `1111` - negative one
- `1110` - negative two
- `1101` - negative three
- `1100` to `1000` - negative four to negative eight

Note that you get one extra value for negatives (`1000` = -8) that you don't for positives. This is because `0000` is used for zero.

Doing this, the first bit gets the role of the "sign" bit, since it is always '1' for negative numbers, and '0' for non-negatives (zero and positive).
