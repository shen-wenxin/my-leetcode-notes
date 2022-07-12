
# 2130. Maximum Twin Sum of a Linked List - 链表最大孪生和

## Tags - 题目标签

 <img src="https://img.shields.io/badge/Stack-栈-blue.svg">   <img src="https://img.shields.io/badge/Linked List-链表-blue.svg">   <img src="https://img.shields.io/badge/Two Pointers-双指针-blue.svg">  


## Description - 题目描述

### EN:
<p>In a linked list of size <code>n</code>, where <code>n</code> is <strong>even</strong>, the <code>i<sup>th</sup></code> node (<strong>0-indexed</strong>) of the linked list is known as the <strong>twin</strong> of the <code>(n-1-i)<sup>th</sup></code> node, if <code>0 &lt;= i &lt;= (n / 2) - 1</code>.</p>

<ul>
	<li>For example, if <code>n = 4</code>, then node <code>0</code> is the twin of node <code>3</code>, and node <code>1</code> is the twin of node <code>2</code>. These are the only nodes with twins for <code>n = 4</code>.</li>
</ul>

<p>The <strong>twin sum </strong>is defined as the sum of a node and its twin.</p>

<p>Given the <code>head</code> of a linked list with even length, return <em>the <strong>maximum twin sum</strong> of the linked list</em>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2021/12/03/eg1drawio.png" style="width: 250px; height: 70px;" />
<pre>
<strong>Input:</strong> head = [5,4,2,1]
<strong>Output:</strong> 6
<strong>Explanation:</strong>
Nodes 0 and 1 are the twins of nodes 3 and 2, respectively. All have twin sum = 6.
There are no other nodes with twins in the linked list.
Thus, the maximum twin sum of the linked list is 6. 
</pre>

<p><strong>Example 2:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2021/12/03/eg2drawio.png" style="width: 250px; height: 70px;" />
<pre>
<strong>Input:</strong> head = [4,2,2,3]
<strong>Output:</strong> 7
<strong>Explanation:</strong>
The nodes with twins present in this linked list are:
- Node 0 is the twin of node 3 having a twin sum of 4 + 3 = 7.
- Node 1 is the twin of node 2 having a twin sum of 2 + 2 = 4.
Thus, the maximum twin sum of the linked list is max(7, 4) = 7. 
</pre>

<p><strong>Example 3:</strong></p>
<img alt="" src="https://assets.leetcode.com/uploads/2021/12/03/eg3drawio.png" style="width: 200px; height: 88px;" />
<pre>
<strong>Input:</strong> head = [1,100000]
<strong>Output:</strong> 100001
<strong>Explanation:</strong>
There is only one node with a twin in the linked list having twin sum of 1 + 100000 = 100001.
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li>The number of nodes in the list is an <strong>even</strong> integer in the range <code>[2, 10<sup>5</sup>]</code>.</li>
	<li><code>1 &lt;= Node.val &lt;= 10<sup>5</sup></code></li>
</ul>


### ZH-CN:
<p>在一个大小为&nbsp;<code>n</code>&nbsp;且 <code>n</code>&nbsp;为&nbsp;<strong>偶数</strong> 的链表中，对于&nbsp;<code>0 &lt;= i &lt;= (n / 2) - 1</code>&nbsp;的 <code>i</code>&nbsp;，第&nbsp;<code>i</code>&nbsp;个节点（下标从 <strong>0</strong>&nbsp;开始）的孪生节点为第&nbsp;<code>(n-1-i)</code>&nbsp;个节点 。</p>

<ul>
	<li>比方说，<code>n = 4</code>&nbsp;那么节点&nbsp;<code>0</code>&nbsp;是节点 <code>3</code>&nbsp;的孪生节点，节点 <code>1</code>&nbsp;是节点 <code>2</code>&nbsp;的孪生节点。这是长度为 <code><span style="">n = 4</span></code>&nbsp;的链表中所有的孪生节点。</li>
</ul>

<p><strong>孪生和</strong>&nbsp;定义为一个节点和它孪生节点两者值之和。</p>

<p>给你一个长度为偶数的链表的头节点&nbsp;<code>head</code>&nbsp;，请你返回链表的 <strong>最大孪生和</strong>&nbsp;。</p>

<p>&nbsp;</p>

<p><strong>示例&nbsp;1：</strong></p>

<p><img alt="" src="https://assets.leetcode.com/uploads/2021/12/03/eg1drawio.png" style="width: 250px; height: 70px;"></p>

<pre><b>输入：</b>head = [5,4,2,1]
<b>输出：</b>6
<strong>解释：</strong>
节点 0 和节点 1 分别是节点 3 和 2 的孪生节点。孪生和都为 6 。
链表中没有其他孪生节点。
所以，链表的最大孪生和是 6 。
</pre>

<p><strong>示例 2：</strong></p>

<p><img alt="" src="https://assets.leetcode.com/uploads/2021/12/03/eg2drawio.png" style="width: 250px; height: 70px;"></p>

<pre><b>输入：</b>head = [4,2,2,3]
<b>输出：</b>7
<strong>解释：</strong>
链表中的孪生节点为：
- 节点 0 是节点 3 的孪生节点，孪生和为 4 + 3 = 7 。
- 节点 1 是节点 2 的孪生节点，孪生和为 2 + 2 = 4 。
所以，最大孪生和为 max(7, 4) = 7 。
</pre>

<p><strong>示例 3：</strong></p>

<p><img alt="" src="https://assets.leetcode.com/uploads/2021/12/03/eg3drawio.png" style="width: 200px; height: 88px;"></p>

<pre><b>输入：</b>head = [1,100000]
<b>输出：</b>100001
<strong>解释：</strong>
链表中只有一对孪生节点，孪生和为 1 + 100000 = 100001 。
</pre>

<p>&nbsp;</p>

<p><strong>提示：</strong></p>

<ul>
	<li>链表的节点数目是&nbsp;<code>[2, 10<sup>5</sup>]</code>&nbsp;中的&nbsp;<strong>偶数</strong>&nbsp;。</li>
	<li><code>1 &lt;= Node.val &lt;= 10<sup>5</sup></code></li>
</ul>



## Link - 题目链接

[LeetCode](https://leetcode.com/problems/maximum-twin-sum-of-a-linked-list/description/)  -  [LeetCode-CN](https://leetcode.cn/problems/maximum-twin-sum-of-a-linked-list/description/)
## Latest Accepted Submissions - 最近一次 AC 的提交


| Language | Runtime | Memory | Submission Time |
|:---:|:---:|:---:|:---:|
| golang  | 176 ms | 9.2 MB | 2022/03/02 20:17 |

```golang

/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func pairSum(head *ListNode) int {

    nums :=[]int{}
    for head != nil{
        nums = append(nums, head.Val)
        head = head.Next

    }
    ans := 1
    n := len(nums)
    for i := 0;i < n/2;i ++{
        sum := nums[i] + nums[n - 1 - i]
        if sum > ans{
            ans = sum
        }
    }
    return ans

}

```
## My Notes - 我的笔记


No notes

