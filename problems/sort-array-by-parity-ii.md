
# 922. Sort Array By Parity II - 按奇偶排序数组 II

## Tags - 题目标签

 <img src="https://img.shields.io/badge/Array-数组-blue.svg">   <img src="https://img.shields.io/badge/Two Pointers-双指针-blue.svg">   <img src="https://img.shields.io/badge/Sorting-排序-blue.svg">  


## Description - 题目描述

### EN:
<p>Given an array of integers <code>nums</code>, half of the integers in <code>nums</code> are <strong>odd</strong>, and the other half are <strong>even</strong>.</p>

<p>Sort the array so that whenever <code>nums[i]</code> is odd, <code>i</code> is <strong>odd</strong>, and whenever <code>nums[i]</code> is even, <code>i</code> is <strong>even</strong>.</p>

<p>Return <em>any answer array that satisfies this condition</em>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> nums = [4,2,5,7]
<strong>Output:</strong> [4,5,2,7]
<strong>Explanation:</strong> [4,7,2,5], [2,5,4,7], [2,7,4,5] would also have been accepted.
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> nums = [2,3]
<strong>Output:</strong> [2,3]
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>2 &lt;= nums.length &lt;= 2 * 10<sup>4</sup></code></li>
	<li><code>nums.length</code> is even.</li>
	<li>Half of the integers in <code>nums</code> are even.</li>
	<li><code>0 &lt;= nums[i] &lt;= 1000</code></li>
</ul>

<p>&nbsp;</p>
<p><strong>Follow Up:</strong> Could you solve it in-place?</p>


### ZH-CN:
<p>给定一个非负整数数组&nbsp;<code>nums</code>，&nbsp;&nbsp;<code>nums</code> 中一半整数是 <strong>奇数</strong> ，一半整数是 <strong>偶数</strong> 。</p>

<p>对数组进行排序，以便当&nbsp;<code>nums[i]</code> 为奇数时，<code>i</code>&nbsp;也是 <strong>奇数</strong> ；当&nbsp;<code>nums[i]</code>&nbsp;为偶数时， <code>i</code> 也是 <strong>偶数</strong> 。</p>

<p>你可以返回 <em>任何满足上述条件的数组作为答案</em> 。</p>

<p>&nbsp;</p>

<p><strong>示例 1：</strong></p>

<pre>
<strong>输入：</strong>nums = [4,2,5,7]
<strong>输出：</strong>[4,5,2,7]
<strong>解释：</strong>[4,7,2,5]，[2,5,4,7]，[2,7,4,5] 也会被接受。
</pre>

<p><strong>示例 2：</strong></p>

<pre>
<b>输入：</b>nums = [2,3]
<b>输出：</b>[2,3]
</pre>

<p>&nbsp;</p>

<p><strong>提示：</strong></p>

<ul>
	<li><code>2 &lt;= nums.length &lt;= 2 * 10<sup>4</sup></code></li>
	<li><code>nums.length</code>&nbsp;是偶数</li>
	<li><code>nums</code>&nbsp;中一半是偶数</li>
	<li><code>0 &lt;= nums[i] &lt;= 1000</code></li>
</ul>

<p>&nbsp;</p>

<p><strong>进阶：</strong>可以不使用额外空间解决问题吗？</p>



## Link - 题目链接

[LeetCode](https://leetcode.com/problems/sort-array-by-parity-ii/description/)  -  [LeetCode-CN](https://leetcode.cn/problems/sort-array-by-parity-ii/description/)
## Latest Accepted Submissions - 最近一次 AC 的提交


| Language | Runtime | Memory | Submission Time |
|:---:|:---:|:---:|:---:|
| golang  | 16 ms | 6.7 MB | 2022/03/09 10:20 |

```golang

func sortArrayByParityII(nums []int) []int {
    nums1 := []int{}
    nums2 := []int{}
    ans := []int{}
    for i:=0 ; i< len(nums); i++{
        if nums[i]%2 == 0{
            nums1=append(nums1, nums[i])
        }else{
            nums2=append(nums2, nums[i])
}
        

}
    for i:=0;i < len(nums1) ;i ++{
        ans = append(ans, nums1[i])
        ans = append(ans, nums2[i])
	
}
return ans

}

```
## My Notes - 我的笔记


No notes

