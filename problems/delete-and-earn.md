
# 740. Delete and Earn - 删除并获得点数

## Tags - 题目标签

 <img src="https://img.shields.io/badge/Array-数组-blue.svg">   <img src="https://img.shields.io/badge/Hash Table-哈希表-blue.svg">   <img src="https://img.shields.io/badge/Dynamic Programming-动态规划-blue.svg">  


## Description - 题目描述

### EN:
<p>You are given an integer array <code>nums</code>. You want to maximize the number of points you get by performing the following operation any number of times:</p>

<ul>
	<li>Pick any <code>nums[i]</code> and delete it to earn <code>nums[i]</code> points. Afterwards, you must delete <b>every</b> element equal to <code>nums[i] - 1</code> and <strong>every</strong> element equal to <code>nums[i] + 1</code>.</li>
</ul>

<p>Return <em>the <strong>maximum number of points</strong> you can earn by applying the above operation some number of times</em>.</p>

<p>&nbsp;</p>
<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> nums = [3,4,2]
<strong>Output:</strong> 6
<strong>Explanation:</strong> You can perform the following operations:
- Delete 4 to earn 4 points. Consequently, 3 is also deleted. nums = [2].
- Delete 2 to earn 2 points. nums = [].
You earn a total of 6 points.
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> nums = [2,2,3,3,3,4]
<strong>Output:</strong> 9
<strong>Explanation:</strong> You can perform the following operations:
- Delete a 3 to earn 3 points. All 2&#39;s and 4&#39;s are also deleted. nums = [3,3].
- Delete a 3 again to earn 3 points. nums = [3].
- Delete a 3 once more to earn 3 points. nums = [].
You earn a total of 9 points.</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>1 &lt;= nums.length &lt;= 2 * 10<sup>4</sup></code></li>
	<li><code>1 &lt;= nums[i] &lt;= 10<sup>4</sup></code></li>
</ul>


### ZH-CN:
<p>给你一个整数数组 <code>nums</code> ，你可以对它进行一些操作。</p>

<p>每次操作中，选择任意一个 <code>nums[i]</code> ，删除它并获得 <code>nums[i]</code> 的点数。之后，你必须删除 <strong>所有 </strong>等于 <code>nums[i] - 1</code> 和 <code>nums[i] + 1</code> 的元素。</p>

<p>开始你拥有 <code>0</code> 个点数。返回你能通过这些操作获得的最大点数。</p>

<p> </p>

<p><strong>示例 1：</strong></p>

<pre>
<strong>输入：</strong>nums = [3,4,2]
<strong>输出：</strong>6
<strong>解释：</strong>
删除 4 获得 4 个点数，因此 3 也被删除。
之后，删除 2 获得 2 个点数。总共获得 6 个点数。
</pre>

<p><strong>示例 2：</strong></p>

<pre>
<strong>输入：</strong>nums = [2,2,3,3,3,4]
<strong>输出：</strong>9
<strong>解释：</strong>
删除 3 获得 3 个点数，接着要删除两个 2 和 4 。
之后，再次删除 3 获得 3 个点数，再次删除 3 获得 3 个点数。
总共获得 9 个点数。
</pre>

<p> </p>

<p><strong>提示：</strong></p>

<ul>
	<li><code>1 <= nums.length <= 2 * 10<sup>4</sup></code></li>
	<li><code>1 <= nums[i] <= 10<sup>4</sup></code></li>
</ul>



## Link - 题目链接

[LeetCode](https://leetcode.com/problems/delete-and-earn/description/)  -  [LeetCode-CN](https://leetcode.cn/problems/delete-and-earn/description/)
## Latest Accepted Submissions - 最近一次 AC 的提交


| Language | Runtime | Memory | Submission Time |
|:---:|:---:|:---:|:---:|
| java  | 3 ms | 38.2 MB | 2021/11/05 14:56 |

```java

class Solution {
    private int getMaxMondy(int [] sum){
        int []dp = new int [sum.length];
        dp[0] = sum[0];
        dp[1] = Math.max(sum[0], sum[1]);
        for(int i = 2;i < sum.length;i ++){
            dp[i] = Math.max(dp[i - 1], dp[i - 2] + sum[i]);
        }
        return dp[sum.length - 1];
    }
    public int deleteAndEarn(int[] nums) {
        //淦，刚开始看的时候没看出来，转眼间发现还是打家劫舍
        // sum[x] 表示选择了x，还可以获得sum[x]的点数
        Arrays.sort(nums);
        int max_num = nums[nums.length - 1];
        int []sum = new int[max_num + 1];
        Arrays.fill(sum,0);//将array置零
        for(int v: nums){
            sum[v] += v;
        }
        //开始调用打家劫舍的方法
        return getMaxMondy(sum);



    }
}

```
## My Notes - 我的笔记


No notes

