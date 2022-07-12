
# 832. Flipping an Image - 翻转图像

## Tags - 题目标签

 <img src="https://img.shields.io/badge/Array-数组-blue.svg">   <img src="https://img.shields.io/badge/Two Pointers-双指针-blue.svg">   <img src="https://img.shields.io/badge/Matrix-矩阵-blue.svg">   <img src="https://img.shields.io/badge/Simulation-模拟-blue.svg">  


## Description - 题目描述

### EN:
<p>Given an <code>n x n</code> binary matrix <code>image</code>, flip the image <strong>horizontally</strong>, then invert it, and return <em>the resulting image</em>.</p>

<p>To flip an image horizontally means that each row of the image is reversed.</p>

<ul>
	<li>For example, flipping <code>[1,1,0]</code> horizontally results in <code>[0,1,1]</code>.</li>
</ul>

<p>To invert an image means that each <code>0</code> is replaced by <code>1</code>, and each <code>1</code> is replaced by <code>0</code>.</p>

<ul>
	<li>For example, inverting <code>[0,1,1]</code> results in <code>[1,0,0]</code>.</li>
</ul>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> image = [[1,1,0],[1,0,1],[0,0,0]]
<strong>Output:</strong> [[1,0,0],[0,1,0],[1,1,1]]
<strong>Explanation:</strong> First reverse each row: [[0,1,1],[1,0,1],[0,0,0]].
Then, invert the image: [[1,0,0],[0,1,0],[1,1,1]]
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> image = [[1,1,0,0],[1,0,0,1],[0,1,1,1],[1,0,1,0]]
<strong>Output:</strong> [[1,1,0,0],[0,1,1,0],[0,0,0,1],[1,0,1,0]]
<strong>Explanation:</strong> First reverse each row: [[0,0,1,1],[1,0,0,1],[1,1,1,0],[0,1,0,1]].
Then invert the image: [[1,1,0,0],[0,1,1,0],[0,0,0,1],[1,0,1,0]]
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>n == image.length</code></li>
	<li><code>n == image[i].length</code></li>
	<li><code>1 &lt;= n &lt;= 20</code></li>
	<li><code>images[i][j]</code> is either <code>0</code> or <code>1</code>.</li>
</ul>


### ZH-CN:
<p>给定一个<meta charset="UTF-8" />&nbsp;<code>n x n</code>&nbsp;的二进制矩阵&nbsp;<code>image</code>&nbsp;，先 <strong>水平</strong> 翻转图像，然后&nbsp;<strong>反转&nbsp;</strong>图像并返回&nbsp;<em>结果</em>&nbsp;。</p>

<p><strong>水平</strong>翻转图片就是将图片的每一行都进行翻转，即逆序。</p>

<ul>
	<li>例如，水平翻转&nbsp;<code>[1,1,0]</code>&nbsp;的结果是&nbsp;<code>[0,1,1]</code>。</li>
</ul>

<p><strong>反转</strong>图片的意思是图片中的&nbsp;<code>0</code>&nbsp;全部被&nbsp;<code>1</code>&nbsp;替换，&nbsp;<code>1</code>&nbsp;全部被&nbsp;<code>0</code>&nbsp;替换。</p>

<ul>
	<li>例如，反转&nbsp;<code>[0,1,1]</code>&nbsp;的结果是&nbsp;<code>[1,0,0]</code>。</li>
</ul>

<p>&nbsp;</p>

<p><strong>示例 1：</strong></p>

<pre>
<strong>输入：</strong>image = [[1,1,0],[1,0,1],[0,0,0]]
<strong>输出：</strong>[[1,0,0],[0,1,0],[1,1,1]]
<strong>解释：</strong>首先翻转每一行: [[0,1,1],[1,0,1],[0,0,0]]；
     然后反转图片: [[1,0,0],[0,1,0],[1,1,1]]
</pre>

<p><strong>示例 2：</strong></p>

<pre>
<strong>输入：</strong>image = [[1,1,0,0],[1,0,0,1],[0,1,1,1],[1,0,1,0]]
<strong>输出：</strong>[[1,1,0,0],[0,1,1,0],[0,0,0,1],[1,0,1,0]]
<strong>解释：</strong>首先翻转每一行: [[0,0,1,1],[1,0,0,1],[1,1,1,0],[0,1,0,1]]；
     然后反转图片: [[1,1,0,0],[0,1,1,0],[0,0,0,1],[1,0,1,0]]
</pre>

<p>&nbsp;</p>

<p><strong>提示：</strong></p>

<p><meta charset="UTF-8" /></p>

<ul>
	<li><code>n == image.length</code></li>
	<li><code>n == image[i].length</code></li>
	<li><code>1 &lt;= n &lt;= 20</code></li>
	<li><code>images[i][j]</code>&nbsp;==&nbsp;<code>0</code>&nbsp;或&nbsp;<code>1</code>.</li>
</ul>



## Link - 题目链接

[LeetCode](https://leetcode.com/problems/flipping-an-image/description/)  -  [LeetCode-CN](https://leetcode.cn/problems/flipping-an-image/description/)
## Latest Accepted Submissions - 最近一次 AC 的提交


| Language | Runtime | Memory | Submission Time |
|:---:|:---:|:---:|:---:|
| golang  | 0 ms | 2.7 MB | 2022/03/04 14:58 |

```golang

func reverse(a []int){
    //翻转
    for i,n := 0, len(a);i < n/2;i ++{
        a[i], a[n - i - 1] = a[n - i - 1], a[i]
    }
}

func rollback(a []int){
    // 反转图片
    for i :=0 ;i < len(a); i ++{
        if a[i] == 0{
            a[i] = 1
        }else{
            a[i] = 0
        }
    } 
}
func flipAndInvertImage(image [][]int) [][]int {
    for _,nums := range image{
        reverse(nums)
        rollback(nums)
    } 
    return image



}

```
## My Notes - 我的笔记


No notes

