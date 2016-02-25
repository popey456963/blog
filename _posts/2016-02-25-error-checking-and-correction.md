---
layout: post
title:  "Error Checking and Correction"
date:   2016/02/25 13:59
categories: [Computing, A-Level, AQA]
permalink: /archive/error-checking-and-correction
---

#### **Parity Check**

Data encoded in binary can be sent electronically. The quality of the electronic communication may not be perfect so there may be errors when the data is received. For example the letter "A" in ASCII is $$1000001_2$$. An error may cause the data received to get corrupted to $$1100001_2$$ which has as different meaning ($$1100001_2$$ means "b").

To help find errors in transmission, messages can be encoded using more bits and then using the extra bits to store values that allow parity checks to be carried out:

We decide whether we are going to use **even parity** or **odd parity**. Even parity means using a value for the parity bit that makes the total number of ones in the byte even. eg $$01000001_2$$ and $$11000011_2$$
If an error occurs and any one of the bits gets swapped, even parity will be broken and the recipient will know that the value is incorrect. eg $$11100011_2$$

Parity checks do **not** provide a means to correct errors but do highlight an error.
A parity check will only detect one error, not two. ie odd number of errors. eg $$11\color{red}{1}0\color{red}{1}011$$ where the red numbers that are incorrect are red. There is even parity but the number is wrong.

#### **Majority Voting**

One other way to detect and correct errors in a transmission is to send a message 3 or more times:

$$\overset{\color{orange}{\downarrow}}{1}\overset{\color{red}{\downarrow}}{1}\overset{\color{purple}{\downarrow}}{1}\ \overset{\color{orange}{\downarrow}}{0}\overset{\color{red}{\downarrow}}{0}\overset{\color{purple}{\downarrow}}{0}\ \overset{\color{orange}{\downarrow}}{0}\overset{\color{red}{\downarrow}}{0}\overset{\color{purple}{\downarrow}}{0}\ \overset{\color{orange}{\downarrow}}{1}\overset{\color{red}{\downarrow}}{1}\overset{\color{purple}{\downarrow}}{1}$$

where each colour arrow shows a different message. If an error occurs it looks like this:

$$\overset{\color{orange}{\downarrow}}{1}\overset{\color{red}{\downarrow}}{1}\overset{\color{purple}{\downarrow}}{1}\ \overset{\color{orange}{\downarrow}}{0}\overset{\color{red}{\downarrow}}{1}\overset{\color{purple}{\downarrow}}{0}\ \overset{\color{orange}{\downarrow}}{0}\overset{\color{red}{\downarrow}}{0}\overset{\color{purple}{\downarrow}}{0}\ \overset{\color{orange}{\downarrow}}{1}\overset{\color{red}{\downarrow}}{1}\overset{\color{purple}{\downarrow}}{1}$$

The error has only occurred in copy 2 so copies 1 and 3 are can be assumed to be correct as they are in the majority.
Broken down into individual steps:

1. The first digit is 1 in all 3 copies so it must be correct.
2. The second digit is 0 in copies 1 and 3 so majority voting concludes that is the correct number.
3. The remaining digits are all the same in all the copies so they must be correct.

Majority voting is used most often is safety critical systems.

#### **Check Digits**
A check digit is a number added to a set of data that ensures that the data has been correctly received. Check digits are commonly used for bar-codes. A simple example may be a system that works by adding up the digits of a number and adding a check digit to make a standard total. The only problem with this is that it doesn't check whether the numbers are out of order.