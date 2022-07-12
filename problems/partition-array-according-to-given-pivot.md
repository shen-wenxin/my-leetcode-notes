
# 2161. Partition Array According to Given Pivot - 根据给定数字划分数组

## Tags - 题目标签

 <img src="https://img.shields.io/badge/Array-数组-blue.svg">   <img src="https://img.shields.io/badge/Two Pointers-双指针-blue.svg">   <img src="https://img.shields.io/badge/Simulation-模拟-blue.svg">  


## Description - 题目描述

### EN:
<p>You are given a <strong>0-indexed</strong> integer array <code>nums</code> and an integer <code>pivot</code>. Rearrange <code>nums</code> such that the following conditions are satisfied:</p>

<ul>
	<li>Every element less than <code>pivot</code> appears <strong>before</strong> every element greater than <code>pivot</code>.</li>
	<li>Every element equal to <code>pivot</code> appears <strong>in between</strong> the elements less than and greater than <code>pivot</code>.</li>
	<li>The <strong>relative order</strong> of the elements less than <code>pivot</code> and the elements greater than <code>pivot</code> is maintained.
	<ul>
		<li>More formally, consider every <code>p<sub>i</sub></code>, <code>p<sub>j</sub></code> where <code>p<sub>i</sub></code> is the new position of the <code>i<sup>th</sup></code> element and <code>p<sub>j</sub></code> is the new position of the <code>j<sup>th</sup></code> element. For elements less than <code>pivot</code>, if <code>i &lt; j</code> and <code>nums[i] &lt; pivot</code> and <code>nums[j] &lt; pivot</code>, then <code>p<sub>i</sub> &lt; p<sub>j</sub></code>. Similarly for elements greater than <code>pivot</code>, if <code>i &lt; j</code> and <code>nums[i] &gt; pivot</code> and <code>nums[j] &gt; pivot</code>, then <code>p<sub>i</sub> &lt; p<sub>j</sub></code>.</li>
	</ul>
	</li>
</ul>

<p>Return <code>nums</code><em> after the rearrangement.</em></p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> nums = [9,12,5,10,14,3,10], pivot = 10
<strong>Output:</strong> [9,5,3,10,10,12,14]
<strong>Explanation:</strong> 
The elements 9, 5, and 3 are less than the pivot so they are on the left side of the array.
The elements 12 and 14 are greater than the pivot so they are on the right side of the array.
The relative ordering of the elements less than and greater than pivot is also maintained. [9, 5, 3] and [12, 14] are the respective orderings.
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> nums = [-3,4,3,2], pivot = 2
<strong>Output:</strong> [-3,2,4,3]
<strong>Explanation:</strong> 
The element -3 is less than the pivot so it is on the left side of the array.
The elements 4 and 3 are greater than the pivot so they are on the right side of the array.
The relative ordering of the elements less than and greater than pivot is also maintained. [-3] and [4, 3] are the respective orderings.
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= nums.length &lt;= 10<sup>5</sup></code></li>
	<li><code>-10<sup>6</sup> &lt;= nums[i] &lt;= 10<sup>6</sup></code></li>
	<li><code>pivot</code> equals to an element of <code>nums</code>.</li>
</ul>


### ZH-CN:
<p>给你一个下标从 <strong>0</strong>&nbsp;开始的整数数组&nbsp;<code>nums</code>&nbsp;和一个整数&nbsp;<code>pivot</code>&nbsp;。请你将&nbsp;<code>nums</code>&nbsp;重新排列，使得以下条件均成立：</p>

<ul>
	<li>所有小于&nbsp;<code>pivot</code>&nbsp;的元素都出现在所有大于&nbsp;<code>pivot</code>&nbsp;的元素&nbsp;<strong>之前</strong>&nbsp;。</li>
	<li>所有等于&nbsp;<code>pivot</code>&nbsp;的元素都出现在小于和大于 <code>pivot</code>&nbsp;的元素 <strong>中间</strong>&nbsp;。</li>
	<li>小于 <code>pivot</code>&nbsp;的元素之间和大于 <code>pivot</code>&nbsp;的元素之间的 <strong>相对顺序</strong>&nbsp;不发生改变。
	<ul>
		<li>更正式的，考虑每一对&nbsp;<code>p<sub>i</sub></code>，<code>p<sub>j</sub></code>&nbsp;，<code>p<sub>i</sub></code>&nbsp;是初始时位置 <code>i</code>&nbsp;元素的新位置，<code>p<sub>j</sub></code>&nbsp;是初始时位置&nbsp;<code>j</code>&nbsp;元素的新位置。对于小于&nbsp;<code>pivot</code>&nbsp;的元素，如果&nbsp;<code>i &lt; j</code>&nbsp;且&nbsp;<code>nums[i] &lt; pivot</code> 和&nbsp;<code>nums[j] &lt; pivot</code>&nbsp;都成立，那么&nbsp;<code>p<sub>i</sub> &lt; p<sub>j</sub></code>&nbsp;也成立。类似的，对于大于&nbsp;<code>pivot</code>&nbsp;的元素，如果&nbsp;<code>i &lt; j</code> 且&nbsp;<code>nums[i] &gt; pivot</code> 和&nbsp;<code>nums[j] &gt; pivot</code>&nbsp;都成立，那么&nbsp;<code>p<sub>i</sub> &lt; p<sub>j</sub></code>&nbsp;。</li>
	</ul>
	</li>
</ul>

<p>请你返回重新排列 <code>nums</code>&nbsp;数组后的结果数组。</p>

<p>&nbsp;</p>

<p><strong>示例 1：</strong></p>

<pre><b>输入：</b>nums = [9,12,5,10,14,3,10], pivot = 10
<b>输出：</b>[9,5,3,10,10,12,14]
<b>解释：</b>
元素 9 ，5 和 3 小于 pivot ，所以它们在数组的最左边。
元素 12 和 14 大于 pivot ，所以它们在数组的最右边。
小于 pivot 的元素的相对位置和大于 pivot 的元素的相对位置分别为 [9, 5, 3] 和 [12, 14] ，它们在结果数组中的相对顺序需要保留。
</pre>

<p><strong>示例 2：</strong></p>

<pre><b>输入：</b>nums = [-3,4,3,2], pivot = 2
<b>输出：</b>[-3,2,4,3]
<b>解释：</b>
元素 -3 小于 pivot ，所以在数组的最左边。
元素 4 和 3 大于 pivot ，所以它们在数组的最右边。
小于 pivot 的元素的相对位置和大于 pivot 的元素的相对位置分别为 [-3] 和 [4, 3] ，它们在结果数组中的相对顺序需要保留。
</pre>

<p>&nbsp;</p>

<p><strong>提示：</strong></p>

<ul>
	<li><code>1 &lt;= nums.length &lt;= 10<sup>5</sup></code></li>
	<li><code>-10<sup>6</sup> &lt;= nums[i] &lt;= 10<sup>6</sup></code></li>
	<li><code>pivot</code>&nbsp;等于&nbsp;<code>nums</code>&nbsp;中的一个元素。</li>
</ul>



## Link - 题目链接

[LeetCode](https://leetcode.com/problems/partition-array-according-to-given-pivot/description/)  -  [LeetCode-CN](https://leetcode.cn/problems/partition-array-according-to-given-pivot/description/)
## Latest Accepted Submissions - 最近一次 AC 的提交


| Language | Runtime | Memory | Submission Time |
|:---:|:---:|:---:|:---:|
| golang  | 176 ms | 9 MB | 2022/03/01 16:22 |

```golang


func reverse(a []int){
    for i, n := 0, len(a);i < n/2 ;i ++{
        a[i], a[n - 1- i ] = a[n - 1- i ],  a[i]
    }
}


func pivotArray(nums []int, pivot int) []int {

    ans := make([]int, len(nums))

    for i := 0;i < len(nums); i++ {
        ans[i] = pivot
    }

    left := 0
    right := len(nums) - 1

    for i := 0;i < len(nums);i ++{
        if nums[i] < pivot{
            ans[left] = nums[i]
            left ++
        }else if nums[i] > pivot{
            ans[right] = nums[i]
            right --
        }
    }

    reverse(ans[right + 1: ])

    return ans

}

```
## My Notes - 我的笔记


No notes

