---
title: "Leetcode 300 Longest Increasing Subsequence (Complete Search with DP) - Cpp"
date: 2021-02-17T23:52:20+02:00
description: "Explaining in video and sharing the code."
tags: [Problem Solving, DP, Leetcode, Backtracking]
---

Today I'm going to resolve, explain and share my c++ solution for 
> 300. Longest Increasing Subsequence on Leetcode

It's the most popular problem in the interviews for complete search so I resolved using recursive backtracking.

## For video explaining

[![Leetcode 300 Longest Increasing Subsequence](https://img.youtube.com/vi/w9ohNqO_4V4/0.jpg)](https://www.youtube.com/watch?v=w9ohNqO_4V4)


## Or jump directly to [the code ](https://github.com/mohamedhafezqo/problem_solving/blob/master/Backtracking/longest-increasing-subsequence.cpp)


```cpp

class Solution {

public:
    vector<vector<int>> memo;
public:
    int lengthOfLIS(vector<int>& nums) {
        int length = nums.size();
        memo.clear();
        memo.resize(length+4, vector<int>(length+4, -1));
        nums.push_back((int)-10e5); //-10000

        int res = dfs(0, length, nums);
        nums.pop_back();
        
        return res;
    }
    
    int dfs(int pos, int last, vector<int>& items) {
        if (pos == items.size() - 1) {
            return 0;
        }
        
        //DB
        if (memo[pos][last] != -1) {
            return memo[pos][last];
        }
        //leave
        int leave = dfs(pos+1, last, items);
        //pick
        int pick = 0;
        if (items[pos] > items[last]) {
            pick = dfs(pos+1, pos, items) + 1;
        }
        
        return memo[pos][last] = max(leave, pick);
    }
};

```




