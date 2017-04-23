---
layout: post
title: Contains Duplicate III
categories: leetcode
tags: [算法, c++]
comments: true
---

* Table of Contents
{:toc}



## 题目

**Given an array of integers, find out whether there are two distinct indices i and j in the array such that the difference between nums[i] and nums[j] is at most t and the difference between i and j is at most k.**



## 解题思路

**维护一个大小为 k 的二叉搜索树，来一个新的元素时，在BST上二分搜索有没有符合条件的数对，动态更新这个BST。因为BST的大小为 k 或不超过 k，所以这里面的数下标的差值一定是符合条件的。直接找nums[i] - t的lower_bound, 这个值就是与nums[i]差值最近的值。**


```cpp
class Solution {
public:
    bool containsNearbyAlmostDuplicate(vector<int>& nums, int k, int t) {
        multiset<long long> bst;
        for (int i = 0; i < nums.size(); ++i) {
            if (bst.size() == k + 1) 
                bst.erase(bst.find(nums[i - k - 1]));
            auto lb = bst.lower_bound(nums[i] - t);
            if (lb != bst.end() && *lb - nums[i] <= t) 
                return true;
            bst.insert(nums[i]);
        }
        return false;
    }
};
```
