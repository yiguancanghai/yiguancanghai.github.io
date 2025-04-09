---
title: "LeetCode 1. Two Sum 两数之和"
date: 2025-04-08 09:00:00 +0800
categories: [算法, 哈希表]
tags: [leetcode, 简单, 数组, 哈希表]
math: true
---

## 题目描述

给定一个整数数组 `nums` 和一个整数目标值 `target`，请你在该数组中找出 **和为目标值** `target` 的那 **两个** 整数，并返回它们的数组下标。

你可以假设每种输入只会对应一个答案。但是，数组中同一个元素在答案里不能重复出现。

你可以按任意顺序返回答案。

**示例：**

输入：nums = [2,7,11,15], target = 9
输出：[0,1]
解释：因为 nums[0] + nums[1] == 9 ，返回 [0, 1]。

## 解题思路

使用一个哈希表（字典）记录已经遍历的数字及其下标。在遍历当前元素时判断 `(target - 当前值)` 是否在字典中：

- 如果存在，就返回下标；
- 如果不存在，就将当前值和下标记录进哈希表。

## 代码实现（Python）

```python
class Solution:
    def twoSum(self, nums, target):
        hashmap = {}
        for i, num in enumerate(nums):
            if target - num in hashmap:
                return [hashmap[target - num], i]
            hashmap[num] = i

复杂度分析
	•	时间复杂度：O(n)，遍历一次数组
	•	空间复杂度：O(n)，哈希表存储元素

总结

哈希表的“边查边存”策略，可以在一次遍历中完成查找和记录，极大提升效率，是“两数之和”类题目的经典方法。