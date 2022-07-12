
# 剑指 Offer 09. 用两个栈实现队列 LCOF - 用两个栈实现队列

## Tags - 题目标签

 <img src="https://img.shields.io/badge/Stack-栈-blue.svg">   <img src="https://img.shields.io/badge/Design-设计-blue.svg">   <img src="https://img.shields.io/badge/Queue-队列-blue.svg">  


## Description - 题目描述

### EN:
English description is not available for the problem. Please switch to Chinese.

### ZH-CN:
<p>用两个栈实现一个队列。队列的声明如下，请实现它的两个函数 <code>appendTail</code> 和 <code>deleteHead</code> ，分别完成在队列尾部插入整数和在队列头部删除整数的功能。(若队列中没有元素，<code>deleteHead</code>&nbsp;操作返回 -1 )</p>

<p>&nbsp;</p>

<p><strong>示例 1：</strong></p>

<pre><strong>输入：</strong>
[&quot;CQueue&quot;,&quot;appendTail&quot;,&quot;deleteHead&quot;,&quot;deleteHead&quot;]
[[],[3],[],[]]
<strong>输出：</strong>[null,null,3,-1]
</pre>

<p><strong>示例 2：</strong></p>

<pre><strong>输入：</strong>
[&quot;CQueue&quot;,&quot;deleteHead&quot;,&quot;appendTail&quot;,&quot;appendTail&quot;,&quot;deleteHead&quot;,&quot;deleteHead&quot;]
[[],[],[5],[2],[],[]]
<strong>输出：</strong>[null,-1,null,null,5,2]
</pre>

<p><strong>提示：</strong></p>

<ul>
	<li><code>1 &lt;= values &lt;= 10000</code></li>
	<li><code>最多会对&nbsp;appendTail、deleteHead 进行&nbsp;10000&nbsp;次调用</code></li>
</ul>



## Link - 题目链接

[LeetCode](https://leetcode.com/problems/yong-liang-ge-zhan-shi-xian-dui-lie-lcof/description/)  -  [LeetCode-CN](https://leetcode.cn/problems/yong-liang-ge-zhan-shi-xian-dui-lie-lcof/description/)
## Latest Accepted Submissions - 最近一次 AC 的提交


| Language | Runtime | Memory | Submission Time |
|:---:|:---:|:---:|:---:|
| python3  | 1536 ms | 18.9 MB | 2021/10/19 11:27 |

```python3

class CQueue:

    def __init__(self):
        self.stack1 = []
        self.stack2 = []



    def appendTail(self, value: int) -> None:
        # stack1 用以新增数据
        # stack2 用以删除数据
        self.stack1.append(value)



    def deleteHead(self) -> int:
        if not self.stack1:
            return -1;
        else:
            # stack1 中有新的数据
            while self.stack1:
                value = self.stack1.pop()
                self.stack2.append(value)
            # 将stack2中的最新的数据弹出来
            result = self.stack2.pop()
            while self.stack2:
                self.stack1.append(self.stack2.pop())
            return result


        




# Your CQueue object will be instantiated and called as such:
# obj = CQueue()
# obj.appendTail(value)
# param_2 = obj.deleteHead()

```
## My Notes - 我的笔记


No notes

