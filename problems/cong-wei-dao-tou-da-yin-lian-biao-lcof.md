
# 剑指 Offer 06. 从尾到头打印链表 LCOF - 从尾到头打印链表

## Tags - 题目标签

 <img src="https://img.shields.io/badge/Stack-栈-blue.svg">   <img src="https://img.shields.io/badge/Recursion-递归-blue.svg">   <img src="https://img.shields.io/badge/Linked List-链表-blue.svg">   <img src="https://img.shields.io/badge/Two Pointers-双指针-blue.svg">  


## Description - 题目描述

### EN:
<p>English description is not available for the problem. Please switch to Chinese.</p>

### ZH-CN:
<p>输入一个链表的头节点，从尾到头反过来返回每个节点的值（用数组返回）。</p>

<p>&nbsp;</p>

<p><strong>示例 1：</strong></p>

<pre><strong>输入：</strong>head = [1,3,2]
<strong>输出：</strong>[2,3,1]</pre>

<p>&nbsp;</p>

<p><strong>限制：</strong></p>

<p><code>0 &lt;= 链表长度 &lt;= 10000</code></p>



## Link - 题目链接

[LeetCode](https://leetcode.com/problems/cong-wei-dao-tou-da-yin-lian-biao-lcof/description/)  -  [LeetCode-CN](https://leetcode.cn/problems/cong-wei-dao-tou-da-yin-lian-biao-lcof/description/)
## Latest Accepted Submissions - 最近一次 AC 的提交


| Language | Runtime | Memory | Submission Time |
|:---:|:---:|:---:|:---:|
| golang  | 0 ms | 3 MB | 2022/03/05 10:17 |

```golang

/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func reverse(a []int){
    for i,n := 0,len(a);i < n/2;i ++{
        a[i], a[n - i - 1] = a[n - i - 1],a[i]
    }
}
func reversePrint(head *ListNode) []int {

    nums := []int{}
    for head != nil{
        nums = append(nums, head.Val)
        head = head.Next
    }
    reverse(nums)
    return nums


}

```
## My Notes - 我的笔记


No notes

