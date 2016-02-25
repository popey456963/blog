---
layout: post
title:  "Bitmap Graphics"
date:   2016/02/24 19:22
categories: [Computing, A-Level, AQA]
permalink: /archive/bitmap-graphics
---

Images are displayed on a computer monitor as bitmaps. A bitmap is a grid of pixels. The pixels may be represented using different numbers of bits which correspond to the number of colours present in the available range.

> **For example:**
> If 1 bit is used to represent the colour of a pixel, it can have 2 values - black and white (colours may vary from monitor to monitor). This is properly described as a **monochrome** although monochrome is usually used to describe a grey scale picture. 
Grey scale

Uses 8 bits to give 256 colours of grey, from black (0) to white (255)

Colour

Normally uses 24 bits to represent levels of red, green and blue:
$$\color{red}{\overset{11111111}{\mathsf{Red}}}\ \ \color{green}{\overset{11111111}{\mathsf{Green}}}\ \ \color{Blue}{\overset{11111111}{\mathsf{Blue}}}$$
These values are often rtepresented as decimal or hex values such as `255,0,255` or `#FF00FF`.
24 bit colour allows for up to $256\times256\times256$. ie $16,777,216$ different colours.
The number of bits used to represent colours in bit maps are called the **bit depth**. 

> **Note about printing**
> Computer displays use (effectively) coloured lights to produce an image. 24-bit colour displays use RGB to represent as many colours as possible. Printers usually use 4 colours: Cyan, Magenta, Yellow and black. Accurate conversion from RGB to CMYK is difficult to achieve 