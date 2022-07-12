
# 35. Search Insert Position - 搜索插入位置

## Tags - 题目标签

 <img src="https://img.shields.io/badge/Array-数组-blue.svg">   <img src="https://img.shields.io/badge/Binary Search-二分查找-blue.svg">  


## Description - 题目描述

### EN:
<p>Given a sorted array of distinct integers and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.</p>

<p>You must&nbsp;write an algorithm with&nbsp;<code>O(log n)</code> runtime complexity.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> nums = [1,3,5,6], target = 5
<strong>Output:</strong> 2
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> nums = [1,3,5,6], target = 2
<strong>Output:</strong> 1
</pre>

<p><strong>Example 3:</strong></p>

<pre>
<strong>Input:</strong> nums = [1,3,5,6], target = 7
<strong>Output:</strong> 4
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= nums.length &lt;= 10<sup>4</sup></code></li>
	<li><code>-10<sup>4</sup> &lt;= nums[i] &lt;= 10<sup>4</sup></code></li>
	<li><code>nums</code> contains <strong>distinct</strong> values sorted in <strong>ascending</strong> order.</li>
	<li><code>-10<sup>4</sup> &lt;= target &lt;= 10<sup>4</sup></code></li>
</ul>


### ZH-CN:
<p>给定一个排序数组和一个目标值，在数组中找到目标值，并返回其索引。如果目标值不存在于数组中，返回它将会被按顺序插入的位置。</p>

<p>请必须使用时间复杂度为 <code>O(log n)</code> 的算法。</p>

<p>&nbsp;</p>

<p><strong>示例 1:</strong></p>

<pre>
<strong>输入:</strong> nums = [1,3,5,6], target = 5
<strong>输出:</strong> 2
</pre>

<p><strong>示例&nbsp;2:</strong></p>

<pre>
<strong>输入:</strong> nums = [1,3,5,6], target = 2
<strong>输出:</strong> 1
</pre>

<p><strong>示例 3:</strong></p>

<pre>
<strong>输入:</strong> nums = [1,3,5,6], target = 7
<strong>输出:</strong> 4
</pre>

<p>&nbsp;</p>

<p><strong>提示:</strong></p>

<ul>
	<li><code>1 &lt;= nums.length &lt;= 10<sup>4</sup></code></li>
	<li><code>-10<sup>4</sup> &lt;= nums[i] &lt;= 10<sup>4</sup></code></li>
	<li><code>nums</code> 为&nbsp;<strong>无重复元素&nbsp;</strong>的&nbsp;<strong>升序&nbsp;</strong>排列数组</li>
	<li><code>-10<sup>4</sup> &lt;= target &lt;= 10<sup>4</sup></code></li>
</ul>



## Link - 题目链接

[LeetCode](https://leetcode.com/problems/search-insert-position/description/)  -  [LeetCode-CN](https://leetcode.cn/problems/search-insert-position/description/)
## Latest Accepted Submissions - 最近一次 AC 的提交


| Language | Runtime | Memory | Submission Time |
|:---:|:---:|:---:|:---:|
| golang  | 4 ms | 2.8 MB | 2022/02/24 15:21 |

```golang

func searchInsert(nums []int, target int) int {
    left := 0
    right := len(nums) - 1
    mid := (left + right) / 2

    if nums[0] >= target {
        return 0
    }
    if nums[right] < target{
        return right + 1
    }

    if nums[right] == target{
        return right
    }

    for{
        if left > right{
            break
        }
        if left + 1 == right{
            if nums[left] != target && nums[right] != target{
                return left + 1
            }
        }
        mid = (left + right) / 2
        if nums[mid] < target{
            left = mid
        }else if nums[mid] > target{
            right = mid
        }else{
            return mid
        }
    }
    return mid

}

```
## My Notes - 我的笔记


No notes

