---
layout:     post
title:      Leetcode： 5.Longest Palindromic Substring
subtitle:   thinkings, disscussion and source code after practicing in Leetcode
date:       2020-02-12
author:     Jyokou
header-img: img/blog-2020-01-06.jpg
catalog: true
tags:
    - data structure
    - algorithm
    - C++
---

# Answer 1
## Code  
```C++
//the recursive formula is T(n)=T(n-1)+O(n^2) (if not consider str.substr())
class Solution {
public:        
        int max=0;
        string max_str="";
    string longestPalindrome(string s) {
        //base case of recurse
        if(s.size()==0) return max_str;
        //deal with and decrease a char from string 
        char tmp=s[s.size()-1];
        for(int i=0;i<s.size();i++){
            if(s[i]==tmp){
                int j=i,k=s.size()-1;
                while(s[j]==s[k] && j<k){
                    j++; k--;
                }
                if(k<=j && max<s.size()-i) {max=s.size()-i; max_str=s.substr(i);}
            }
        }
        s=s.erase(s.size()-1);
        //consider the T(n-1)
        return longestPalindrome(s);
        
    }
};
```
## Result  
Exceed time limition

## Explanation
**Decrease-and-conquer** and **Recurse** are employed in this method. If not consider the time of function *str.substr()*,the time complexity of the algorithm is **O($n^3$)**. 