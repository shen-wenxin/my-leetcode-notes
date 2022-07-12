
# 5. Longest Palindromic Substring - 最长回文子串

## Tags - 题目标签

 <img src="https://img.shields.io/badge/String-字符串-blue.svg">   <img src="https://img.shields.io/badge/Dynamic Programming-动态规划-blue.svg">  


## Description - 题目描述

### EN:
<p>Given a string <code>s</code>, return <em>the longest palindromic substring</em> in <code>s</code>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> s = &quot;babad&quot;
<strong>Output:</strong> &quot;bab&quot;
<strong>Explanation:</strong> &quot;aba&quot; is also a valid answer.
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> s = &quot;cbbd&quot;
<strong>Output:</strong> &quot;bb&quot;
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= s.length &lt;= 1000</code></li>
	<li><code>s</code> consist of only digits and English letters.</li>
</ul>


### ZH-CN:
<p>给你一个字符串 <code>s</code>，找到 <code>s</code> 中最长的回文子串。</p>

<p>&nbsp;</p>

<p><strong>示例 1：</strong></p>

<pre>
<strong>输入：</strong>s = "babad"
<strong>输出：</strong>"bab"
<strong>解释：</strong>"aba" 同样是符合题意的答案。
</pre>

<p><strong>示例 2：</strong></p>

<pre>
<strong>输入：</strong>s = "cbbd"
<strong>输出：</strong>"bb"
</pre>

<p>&nbsp;</p>

<p><strong>提示：</strong></p>

<ul>
	<li><code>1 &lt;= s.length &lt;= 1000</code></li>
	<li><code>s</code> 仅由数字和英文字母组成</li>
</ul>



## Link - 题目链接

[LeetCode](https://leetcode.com/problems/longest-palindromic-substring/description/)  -  [LeetCode-CN](https://leetcode.cn/problems/longest-palindromic-substring/description/)
## Latest Accepted Submissions - 最近一次 AC 的提交


| Language | Runtime | Memory | Submission Time |
|:---:|:---:|:---:|:---:|
| cpp  | 388 ms | 11.2 MB | 2021/10/28 15:29 |

```cpp

class Solution {
public:
    string longestPalindrome(string s) {
        int len = s.length();
        if(len < 2){
            //考虑只有一个 元素的情况
            return s;
        }
        int dp[len + 1][len + 1];
        memset(dp,0,sizeof(dp));
        int max_length = 1;
        int begin = 0;
        for(int L = 2;L <= len;L ++){
            //开始遍历子串的长度
            for(int i = 0;i < len;i ++){
                //遍历子串
                int j = i + L - 1;
                if(j >= len){
                    break;
                }
                if(s[i] != s[j]){
                    dp[i][j] = 0;
                }
                else{
                    if(j - i < 3){
                        dp[i][j] = 1;
                    }
                    else{
                        dp[i][j] = dp[i + 1][j - 1]; 
                    }
                }
                if(dp[i][j] && max_length < L){
                    max_length = L;
                    begin = i;
                }

            }
        }
        return s.substr(begin,max_length);


    }
};

```
## My Notes - 我的笔记


No notes

