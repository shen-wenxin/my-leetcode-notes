
# 面试题 02.02. Kth Node From End of List LCCI - 返回倒数第 k 个节点

## Tags - 题目标签

 <img src="https://img.shields.io/badge/Linked List-链表-blue.svg">   <img src="https://img.shields.io/badge/Two Pointers-双指针-blue.svg">  


## Description - 题目描述

### EN:
<p>Implement an algorithm to find the kth to last element of a singly linked list.&nbsp;Return the value of the element.</p>

<p><strong>Note: </strong>This problem is slightly different from the original one in the book.</p>

<p><strong>Example: </strong></p>

<pre>
<strong>Input: </strong> 1-&gt;2-&gt;3-&gt;4-&gt;5 和 <em>k</em> = 2
<strong>Output:  </strong>4</pre>

<p><strong>Note: </strong></p>

<p>k is always valid.</p>


### ZH-CN:
<p>实现一种算法，找出单向链表中倒数第 k 个节点。返回该节点的值。</p>

<p><strong>注意：</strong>本题相对原题稍作改动</p>

<p><strong>示例：</strong></p>

<pre><strong>输入：</strong> 1-&gt;2-&gt;3-&gt;4-&gt;5 和 <em>k</em> = 2
<strong>输出： </strong>4</pre>

<p><strong>说明：</strong></p>

<p>给定的 <em>k</em>&nbsp;保证是有效的。</p>



## Link - 题目链接

[LeetCode](https://leetcode.com/problems/kth-node-from-end-of-list-lcci/description/)  -  [LeetCode-CN](https://leetcode.cn/problems/kth-node-from-end-of-list-lcci/description/)
## Latest Accepted Submissions - 最近一次 AC 的提交


| Language | Runtime | Memory | Submission Time |
|:---:|:---:|:---:|:---:|
| golang  | 0 ms | 2.1 MB | 2022/03/05 1:59 |

```golang

/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func kthToLast(head *ListNode, k int) int {
    nums := []int{}
    for head != nil{
        nums = append(nums, head.Val)
        head = head.Next
    }
    return nums[len(nums) - k]

}

```
## My Notes - 我的笔记


No notes

