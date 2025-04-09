
---
title: "LeetCode 1. Two Sum 两数之和"
date: 2025-04-08 09:00:00 +0800
categories: [算法, 哈希表]
tags: [leetcode, 简单, 数组, 哈希表]
---

## 题目描述

给定一个整数数组 `nums` 和一个整数目标值 `target`，请你在该数组中找出 **和为目标值** `target` 的那 **两个** 整数，并返回它们的数组下标。

**示例:**

输入：nums = [2,7,11,15], target = 9
输出：[0,1]

## 解题思路

使用哈希表存储已经遍历过的数字和它们的下标，边遍历边查找。

```python
class Solution:
    def twoSum(self, nums, target):
        hashmap = {}
        for i, num in enumerate(nums):
            if target - num in hashmap:
                return [hashmap[target - num], i]
            hashmap[num] = i

复杂度分析
	•	时间复杂度：O(n)
	•	空间复杂度：O(n)

总结

边查边存的哈希表思想，是解决“两数之和”类问题的经典解法。