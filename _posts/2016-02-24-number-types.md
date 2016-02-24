---
layout: post
title:  "Number Types"
date:   2016/02/24 15:33
categories: [Computing, A-Level, AQA]
permalink: /archive/number-types
---

#### **Natural numbers**
Numbers that are used by people every day for counting and ordering:
$$0,1,2,3,4,5,6,7,8,9$$
This is called *decimal* or *base-10*. With a single digit, the largest value that can be represented is *9*. To create large numbers we add a new digit to to the left to give the numbers 10...99 and so on.

- Each extra digit is worth ten times the previous digit.
- This idea is important because it applies to other number systems as well.
- We can use this number system to represent an infinite range on numbers.
	- The natural numbers range from $$0 \to \infty$$
- The inclusion of zero is important in programming because arrays and looping structures usually start from 0.

The set of natural numbers has the symbol $$\mathbb{N}$$ so we can write:
$$\mathbb{N} = \{0,1,2,3,4,5,6,7,8,9,...\}$$

#### **Integer numbers**
An integer is a whole number whose value can be either negative or positive. *0* is classed as an integer. 
A whole number does not contain a fractional part (ie. No fractions or decimal points).

- Negative values are pre-seeded by a minus sign ("$$-$$"). $$
(-3 + 3 = 0) \equiv (3 + (-3) = 0)$$

>The word **Bit** is a contraction of <b>Bi</b>nary dig<b>it</b>

Integers are a standard data type used in most programming languages. They are used for variables and constants.
For example in visual basic, an integer is stored in 4 bytes and can store values from -214748364<b>8</b> to 214748364<b>7</b>. The positive numbers are smaller because the range includes 0. Values out of this range are stored in a different data type called *Long* in visual basic.
The symbol for integers is $$\mathbb{Z}$$ (Zahlen). So we can write:

$$\mathbb{Z} = \{\ldots,-2,-1,0,1,2,3,4,5,6,7,8,9,\ldots\}$$

#### **Rational Numbers**

A rational number is one that can be expressed as a fraction. Fractions are made up from 2 integers, with the value being the ration between the 2 integers.
Rational numbers can be represented by a fraction or the decimal equivalent.:

$$\frac{1}{2}\; or  \;0.5$$

The top integer is called the **numerator** and the bottom integer is called the **denominator**. The number can be any integer - any whole number. The values of fractions can be positive or negative, and greater or less than 1 (or 0).

$$
\frac{5}{5}=1
$$

$$
\frac{12}{12}= 1
$$

$$
\frac{12}{6}= 2
$$

As these examples show, all integers can also be expressed as rational numbers. The denominator can have any value except 0. Dividing by 0 gives an indeterminate value and a divide by 0 gives a zero-error in most languages.
The symbol for the set of rational numbers is $$\mathbb{Q}$$.
	  
#### **Irrational Numbers**

An irrational number is any number that cannot be represented as a ratio of integers because the decimal equivalent goes on forever without repeating. A classic example of an irrational number is $$\pi$$ (pi). The commonly used approximation for $$\pi$$ is $$^{22}\!/\!_7$$. In decimal form the number has an infinite number of decimal places so it has to be truncated to a set of decimal places.

Eg: $$3.14159265...$$ or $$3.141$$

More decimal places gives greater **precision**. 

$$\sqrt{2} = 1.414$$ to 3 decimal places.

>NB:
>$$1.414^2\neq2$$ so be careful when approximating.
>  
>  Also, 
>    
>  $$^{1}\!/\!_3 = 0.3333\dot{3}$$ is **NOT** an irratioinal number because:
>  1. It is the ratio between 2 integers
>  2. The digits of the decimal **do** repeat.

For programmers it is important to consider the precision that is needed when using irrational numbers. The programmer needs to decide what precision to use. However, this option is not always available.

For example, in Python:

~~~ python
>>> import math
>>> math.pi
3.141592653589793
>>> # You have no choice as to how many decimal places pi is given to.
~~~
