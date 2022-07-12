
# 2149. Rearrange Array Elements by Sign - 按符号重排数组

## Tags - 题目标签

 <img src="https://img.shields.io/badge/Array-数组-blue.svg">   <img src="https://img.shields.io/badge/Two Pointers-双指针-blue.svg">   <img src="https://img.shields.io/badge/Simulation-模拟-blue.svg">  


## Description - 题目描述

### EN:
<p>You are given a <strong>0-indexed</strong> integer array <code>nums</code> of <strong>even</strong> length consisting of an <strong>equal</strong> number of positive and negative integers.</p>

<p>You should <strong>rearrange</strong> the elements of <code>nums</code> such that the modified array follows the given conditions:</p>

<ol>
	<li>Every <strong>consecutive pair</strong> of integers have <strong>opposite signs</strong>.</li>
	<li>For all integers with the same sign, the <strong>order</strong> in which they were present in <code>nums</code> is <strong>preserved</strong>.</li>
	<li>The rearranged array begins with a positive integer.</li>
</ol>

<p>Return <em>the modified array after rearranging the elements to satisfy the aforementioned conditions</em>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> nums = [3,1,-2,-5,2,-4]
<strong>Output:</strong> [3,-2,1,-5,2,-4]
<strong>Explanation:</strong>
The positive integers in nums are [3,1,2]. The negative integers are [-2,-5,-4].
The only possible way to rearrange them such that they satisfy all conditions is [3,-2,1,-5,2,-4].
Other ways such as [1,-2,2,-5,3,-4], [3,1,2,-2,-5,-4], [-2,3,-5,1,-4,2] are incorrect because they do not satisfy one or more conditions.  
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> nums = [-1,1]
<strong>Output:</strong> [1,-1]
<strong>Explanation:</strong>
1 is the only positive integer and -1 the only negative integer in nums.
So nums is rearranged to [1,-1].
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>2 &lt;= nums.length &lt;= 2 * 10<sup>5</sup></code></li>
	<li><code>nums.length</code> is <strong>even</strong></li>
	<li><code>1 &lt;= |nums[i]| &lt;= 10<sup>5</sup></code></li>
	<li><code>nums</code> consists of <strong>equal</strong> number of positive and negative integers.</li>
</ul>


### ZH-CN:
<p>给你一个下标从 <strong>0</strong> 开始的整数数组 <code>nums</code> ，数组长度为 <strong>偶数</strong> ，由数目相等的正整数和负整数组成。</p>

<p>你需要 <strong>重排</strong> <code>nums</code> 中的元素，使修改后的数组满足下述条件：</p>

<ol>
	<li>任意&nbsp;<strong>连续</strong> 的两个整数 <strong>符号相反</strong></li>
	<li>对于符号相同的所有整数，<strong>保留</strong> 它们在 <code>nums</code> 中的 <strong>顺序</strong> 。</li>
	<li>重排后数组以正整数开头。</li>
</ol>

<p>重排元素满足上述条件后，返回修改后的数组。</p>

<p>&nbsp;</p>

<p><strong>示例 1：</strong></p>

<pre>
<strong>输入：</strong>nums = [3,1,-2,-5,2,-4]
<strong>输出：</strong>[3,-2,1,-5,2,-4]
<strong>解释：</strong>
nums 中的正整数是 [3,1,2] ，负整数是 [-2,-5,-4] 。
重排的唯一可行方案是 [3,-2,1,-5,2,-4]，能满足所有条件。
像 [1,-2,2,-5,3,-4]、[3,1,2,-2,-5,-4]、[-2,3,-5,1,-4,2] 这样的其他方案是不正确的，因为不满足一个或者多个条件。 
</pre>

<p><strong>示例 2：</strong></p>

<pre>
<strong>输入：</strong>nums = [-1,1]
<strong>输出：</strong>[1,-1]
<strong>解释：</strong>
1 是 nums 中唯一一个正整数，-1 是 nums 中唯一一个负整数。
所以 nums 重排为 [1,-1] 。
</pre>

<p>&nbsp;</p>

<p><strong>提示：</strong></p>

<ul>
	<li><code>2 &lt;= nums.length &lt;= 2 * 10<sup>5</sup></code></li>
	<li><code>nums.length</code> 是 <strong>偶数</strong></li>
	<li><code>1 &lt;= |nums[i]| &lt;= 10<sup>5</sup></code></li>
	<li><code>nums</code> 由 <strong>相等</strong> 数量的正整数和负整数组成</li>
</ul>



## Link - 题目链接

[LeetCode](https://leetcode.com/problems/rearrange-array-elements-by-sign/description/)  -  [LeetCode-CN](https://leetcode.cn/problems/rearrange-array-elements-by-sign/description/)
## Latest Accepted Submissions - 最近一次 AC 的提交


| Language | Runtime | Memory | Submission Time |
|:---:|:---:|:---:|:---:|
| golang  | 192 ms | 13.2 MB | 2022/03/03 14:58 |

```golang

func rearrangeArray(nums []int) []int {
    // 双指针 用pos 指向正数 neg指向负数
    pos := 0
    neg := 0
    ans := []int{}
    for{
        if len(ans) == len(nums){
            return ans
        }
        for nums[pos] < 0{
            pos ++
        }
        for nums[neg] > 0{
            neg ++
        }
        ans = append(ans, nums[pos])
        ans = append(ans, nums[neg])
        pos ++
        neg ++
    }
    return ans


}

```
## My Notes - 我的笔记


No notes

