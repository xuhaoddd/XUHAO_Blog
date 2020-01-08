---
layout:     post
title:      Leetcode Notes
subtitle:   leetcode 1
date:       2020-01-08
author:     Jyokou
header-img: img/blog-2020-01-06.jpg
catalog: true
tags:
    - data structure
    - algorithm
    - C++
---
# **Leetcode 1**

## **Exercise Description**

Given an array of integers, return indices of the two numbers such that they add up to a specific target.You may assume that each input would have exactly one solution, and you may not use the same element twice.

Example:
>Given nums = [2, 7, 11, 15], target = 9,  
>Because nums[0] + nums[1] = 2 + 7 = 9,  
>return [0, 1].

## **code**
- **Source code**
```
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        vector<int> tmp(2);
        for(int i=0;i<nums.size();i++)
        for(int j=0;j<nums.size();j++){
            if(nums[i]+nums[j]==target && i!=j){
                if(i<j){
                tmp[0]=i;
                tmp[1]=j;    
                }
                else{
                    tmp[0]=j;
                    tmp[1]=i; 
                }

            }
        }
        return tmp;
    }
}; 
```
- **Analysis**  
    The array is traversed two times by two-layer loop.  

    If the condition of the sum of two numbers equal to the target number is satisfied, the two numbers will be output.  
    
    Time complexity is __O($n^2$)__ and space complexity is **O(1)**  

- **Inspiration**  
  There are other solutions to this problem  
  1. 







