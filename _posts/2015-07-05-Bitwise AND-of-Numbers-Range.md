---
layout: post
title: Bitwise AND of Numbers Range
categories: leetcode
tags: [算法, c++]
comments: true
---

* Table of Contents
{:toc}



## 题目

~~~
Given a range [m, n] where 0 <= m <= n <= 2147483647, return the bitwise AND of all numbers in this range, inclusive.

For example, given the range [5, 7], you should return 4.
~~~



## 解题思路

**将m与n不断右移，同时记录位移的位数p，直到两数相等。m再左移p位就是结果。技巧是，只要某一位出现了0，则这一位必然为0.**.


```cpp
class Solution {
public:
    int rangeBitwiseAnd(int m, int n) {
        int p = 0;
        while (m != n)
        {
            m = m>>1;
            n = n>>1;
            p++;
        }  
        return m<<p;
    }
};
```
