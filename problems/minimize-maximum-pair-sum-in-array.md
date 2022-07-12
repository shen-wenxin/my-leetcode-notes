
# 1877. Minimize Maximum Pair Sum in Array - 数组中最大数对和的最小值

## Tags - 题目标签

 <img src="https://img.shields.io/badge/Greedy-贪心-blue.svg">   <img src="https://img.shields.io/badge/Array-数组-blue.svg">   <img src="https://img.shields.io/badge/Two Pointers-双指针-blue.svg">   <img src="https://img.shields.io/badge/Sorting-排序-blue.svg">  


## Description - 题目描述

### EN:
<p>The <strong>pair sum</strong> of a pair <code>(a,b)</code> is equal to <code>a + b</code>. The <strong>maximum pair sum</strong> is the largest <strong>pair sum</strong> in a list of pairs.</p>

<ul>
	<li>For example, if we have pairs <code>(1,5)</code>, <code>(2,3)</code>, and <code>(4,4)</code>, the <strong>maximum pair sum</strong> would be <code>max(1+5, 2+3, 4+4) = max(6, 5, 8) = 8</code>.</li>
</ul>

<p>Given an array <code>nums</code> of <strong>even</strong> length <code>n</code>, pair up the elements of <code>nums</code> into <code>n / 2</code> pairs such that:</p>

<ul>
	<li>Each element of <code>nums</code> is in <strong>exactly one</strong> pair, and</li>
	<li>The <strong>maximum pair sum </strong>is <strong>minimized</strong>.</li>
</ul>

<p>Return <em>the minimized <strong>maximum pair sum</strong> after optimally pairing up the elements</em>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> nums = [3,5,2,3]
<strong>Output:</strong> 7
<strong>Explanation:</strong> The elements can be paired up into pairs (3,3) and (5,2).
The maximum pair sum is max(3+3, 5+2) = max(6, 7) = 7.
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> nums = [3,5,4,2,4,6]
<strong>Output:</strong> 8
<strong>Explanation:</strong> The elements can be paired up into pairs (3,5), (4,4), and (6,2).
The maximum pair sum is max(3+5, 4+4, 6+2) = max(8, 8, 8) = 8.
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>n == nums.length</code></li>
	<li><code>2 &lt;= n &lt;= 10<sup>5</sup></code></li>
	<li><code>n</code> is <strong>even</strong>.</li>
	<li><code>1 &lt;= nums[i] &lt;= 10<sup>5</sup></code></li>
</ul>

### ZH-CN:
<p>一个数对 <code>(a,b)</code> 的 <strong>数对和</strong> 等于 <code>a + b</code> 。<strong>最大数对和</strong> 是一个数对数组中最大的 <strong>数对和</strong> 。</p>

<ul>
	<li>比方说，如果我们有数对 <code>(1,5)</code> ，<code>(2,3)</code> 和 <code>(4,4)</code>，<strong>最大数对和</strong> 为 <code>max(1+5, 2+3, 4+4) = max(6, 5, 8) = 8</code> 。</li>
</ul>

<p>给你一个长度为 <strong>偶数</strong> <code>n</code> 的数组 <code>nums</code> ，请你将 <code>nums</code> 中的元素分成 <code>n / 2</code> 个数对，使得：</p>

<ul>
	<li><code>nums</code> 中每个元素 <strong>恰好</strong> 在 <strong>一个</strong> 数对中，且</li>
	<li><strong>最大数对和</strong> 的值 <strong>最小</strong> 。</li>
</ul>

<p>请你在最优数对划分的方案下，返回最小的 <strong>最大数对和</strong> 。</p>

<p> </p>

<p><strong>示例 1：</strong></p>

<pre><b>输入：</b>nums = [3,5,2,3]
<b>输出：</b>7
<b>解释：</b>数组中的元素可以分为数对 (3,3) 和 (5,2) 。
最大数对和为 max(3+3, 5+2) = max(6, 7) = 7 。
</pre>

<p><strong>示例 2：</strong></p>

<pre><b>输入：</b>nums = [3,5,4,2,4,6]
<b>输出：</b>8
<b>解释：</b>数组中的元素可以分为数对 (3,5)，(4,4) 和 (6,2) 。
最大数对和为 max(3+5, 4+4, 6+2) = max(8, 8, 8) = 8 。
</pre>

<p> </p>

<p><strong>提示：</strong></p>

<ul>
	<li><code>n == nums.length</code></li>
	<li><code>2 &lt;= n &lt;= 10<sup>5</sup></code></li>
	<li><code>n</code> 是 <strong>偶数</strong> 。</li>
	<li><code>1 &lt;= nums[i] &lt;= 10<sup>5</sup></code></li>
</ul>



## Link - 题目链接

[LeetCode](https://leetcode.com/problems/minimize-maximum-pair-sum-in-array/description/)  -  [LeetCode-CN](https://leetcode.cn/problems/minimize-maximum-pair-sum-in-array/description/)
## Latest Accepted Submissions - 最近一次 AC 的提交


| Language | Runtime | Memory | Submission Time |
|:---:|:---:|:---:|:---:|
| golang  | 244 ms | 8.9 MB | 2022/03/02 20:51 |

```golang

func mymax(a int, b int) int{
    if a > b {
        return a
    }
    return b
}
func minPairSum(nums []int) int {
    sort.Ints(nums)

    ans := 0
    n := len(nums)
    for i := 0;i < n;i ++{
        ans = mymax(ans, nums[i] + nums[n - i - 1])
    }

    return ans

}

```
## My Notes - 我的笔记


No notes

