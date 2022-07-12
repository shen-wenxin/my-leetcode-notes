
# 349. Intersection of Two Arrays - 两个数组的交集

## Tags - 题目标签

 <img src="https://img.shields.io/badge/Array-数组-blue.svg">   <img src="https://img.shields.io/badge/Hash Table-哈希表-blue.svg">   <img src="https://img.shields.io/badge/Two Pointers-双指针-blue.svg">   <img src="https://img.shields.io/badge/Binary Search-二分查找-blue.svg">   <img src="https://img.shields.io/badge/Sorting-排序-blue.svg">  


## Description - 题目描述

### EN:
<p>Given two integer arrays <code>nums1</code> and <code>nums2</code>, return <em>an array of their intersection</em>. Each element in the result must be <strong>unique</strong> and you may return the result in <strong>any order</strong>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> nums1 = [1,2,2,1], nums2 = [2,2]
<strong>Output:</strong> [2]
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> nums1 = [4,9,5], nums2 = [9,4,9,8,4]
<strong>Output:</strong> [9,4]
<strong>Explanation:</strong> [4,9] is also accepted.
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= nums1.length, nums2.length &lt;= 1000</code></li>
	<li><code>0 &lt;= nums1[i], nums2[i] &lt;= 1000</code></li>
</ul>


### ZH-CN:
<p>给定两个数组&nbsp;<code>nums1</code>&nbsp;和&nbsp;<code>nums2</code> ，返回 <em>它们的交集</em>&nbsp;。输出结果中的每个元素一定是 <strong>唯一</strong> 的。我们可以 <strong>不考虑输出结果的顺序</strong> 。</p>

<p>&nbsp;</p>

<p><strong>示例 1：</strong></p>

<pre>
<strong>输入：</strong>nums1 = [1,2,2,1], nums2 = [2,2]
<strong>输出：</strong>[2]
</pre>

<p><strong>示例 2：</strong></p>

<pre>
<strong>输入：</strong>nums1 = [4,9,5], nums2 = [9,4,9,8,4]
<strong>输出：</strong>[9,4]
<strong>解释：</strong>[4,9] 也是可通过的
</pre>

<p>&nbsp;</p>

<p><strong>提示：</strong></p>

<ul>
	<li><code>1 &lt;= nums1.length, nums2.length &lt;= 1000</code></li>
	<li><code>0 &lt;= nums1[i], nums2[i] &lt;= 1000</code></li>
</ul>



## Link - 题目链接

[LeetCode](https://leetcode.com/problems/intersection-of-two-arrays/description/)  -  [LeetCode-CN](https://leetcode.cn/problems/intersection-of-two-arrays/description/)
## Latest Accepted Submissions - 最近一次 AC 的提交


| Language | Runtime | Memory | Submission Time |
|:---:|:---:|:---:|:---:|
| golang  | 4 ms | 2.6 MB | 2022/03/08 10:49 |

```golang

func intersection(nums1 []int, nums2 []int) []int {
    sort.Ints(nums1)
    sort.Ints(nums2)

    // fmt.Println(nums1)
    // fmt.Println(nums2)
    n1 := 0
    n2 := 0
    ans := []int{}
    n3 := 0

    for{
        
        if n1 == len(nums1) || n2 == len(nums2){
            return ans
        }
        // fmt.Println(nums1[n1],nums2[n2])
        if nums1[n1] == nums2[n2]{
            if n3 == 0 ||ans[n3 - 1] != nums1[n1]{
                // fmt.Println("get in")
                ans = append(ans, nums1[n1])
                // fmt.Println(ans)
                n3 ++
                n1 ++
                n2 ++
                continue
            }
        }
        if nums1[n1] > nums2[n2]{
            n2 ++
        }else{
            n1 ++
        }
        
    }
    return nums1

}

```
## My Notes - 我的笔记


No notes

