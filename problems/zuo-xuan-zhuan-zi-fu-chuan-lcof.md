
# 剑指 Offer 58 - II. 左旋转字符串 LCOF - 左旋转字符串

## Tags - 题目标签

 <img src="https://img.shields.io/badge/Math-数学-blue.svg">   <img src="https://img.shields.io/badge/Two Pointers-双指针-blue.svg">   <img src="https://img.shields.io/badge/String-字符串-blue.svg">  


## Description - 题目描述

### EN:
<p>English description is not available for the problem. Please switch to Chinese.</p>


### ZH-CN:
<p>字符串的左旋转操作是把字符串前面的若干个字符转移到字符串的尾部。请定义一个函数实现字符串左旋转操作的功能。比如，输入字符串&quot;abcdefg&quot;和数字2，该函数将返回左旋转两位得到的结果&quot;cdefgab&quot;。</p>

<p>&nbsp;</p>

<p><strong>示例 1：</strong></p>

<pre><strong>输入:</strong> s = &quot;abcdefg&quot;, k = 2
<strong>输出:&nbsp;</strong>&quot;cdefgab&quot;
</pre>

<p><strong>示例 2：</strong></p>

<pre><strong>输入:</strong> s = &quot;lrloseumgh&quot;, k = 6
<strong>输出:&nbsp;</strong>&quot;umghlrlose&quot;
</pre>

<p>&nbsp;</p>

<p><strong>限制：</strong></p>

<ul>
	<li><code>1 &lt;= k &lt; s.length &lt;= 10000</code></li>
</ul>



## Link - 题目链接

[LeetCode](https://leetcode.com/problems/zuo-xuan-zhuan-zi-fu-chuan-lcof/description/)  -  [LeetCode-CN](https://leetcode.cn/problems/zuo-xuan-zhuan-zi-fu-chuan-lcof/description/)
## Latest Accepted Submissions - 最近一次 AC 的提交


| Language | Runtime | Memory | Submission Time |
|:---:|:---:|:---:|:---:|
| golang  | 0 ms | 3.1 MB | 2022/03/01 18:37 |

```golang

func reverse(ans []byte ){
    for i, n :=0, len(ans);i < n/2;i ++{
        ans[i], ans[n - 1- i ] =  ans[n - 1- i ], ans[i]
    }
}

func reverseLeftWords(s string, n int) string {
    
    // 这题也可以用翻转的方法写
    ans := []byte(s)

    reverse(ans)
    reverse(ans[0:len(s) - n])
    reverse(ans[len(s) - n:])
    return string(ans)


}

```
## My Notes - 我的笔记


No notes

