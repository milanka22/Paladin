##一面
自我介绍...
自己挑一个项目介绍一下: 这里问的比较详细，具体问到了我的项目每个优化点以及优化的效果，其中还讨论到了TLB，我们对TLB的认识产生的分歧，纠结了一会,觉得TLB, cache, 页表等操作系统的东西还是要多看看书，不能犯特别低级的错误


###算法题
>	给你一个整数数组，找出数组中最大的两个数

我的解法就是类似top k的思路，不过不同于top k因为这里是top 2所以就不必使用堆了，代码如下:

```C++
vector<int> maxTwo(vector<int> &values){
	if(values.size() <= 2)	return values;
	vector<int> res{values[0], values[1]};
	for(int i = 2; i < values.size(); i++){
		if(values[i] > min(res[0], res[1])){
			res[0] = max(res[0], res[1]);
			res[1] = values[i];
		}
	}
	return res;
}
```

>	给你一个无序正整数数组，其中只有一个树出现了两次，其余的数都只出现一次，找出这个出现两次的数

这题它只给了我这么多信息，我先是告诉了他基于hash的做法，他说这个空间复杂度有点高；然后我说用桶排序，维持0~9号这个十个桶，然后数据存放在链表中再与桶关联，做一下桶排序，然后排序好遍历一边就可以找到了,他说这个桶排序需要链表，而链表的话就得额外的花费next指针的空间，合计空间复杂度O(n)也有点多;然后我实在没辙，我就说用bit map的哈希把，这样会减少7/8的空间复杂度,他说这还是不够好，然后就说你回去再想想吧.

从上面的交流看，感觉似乎有一种很巧妙的办法，但是我实在想不到还有比时间O(n)和空间O(n)这种解法还好的解法了．



##二面

二面先是问了一下项目，这次叫我说一说在实验室做的项目，主要侧重点在于项目的背景，怎么想的，如何合作等behavior的问题

###算法题

>	两个字符串的最长公共子串

我就使用动态规划提出了一种O(n^2)复杂度的算法:

dp[i][j]表示s1串从i开始向前与s2串从j开始向前的最长匹配长度,于是target = max{dp[i][j]}

其中，if s1[i] == s2[j] dp[i][j] = dp[i-1][j-1] + 1 else dp[i][j] = 0

然后，并没有写具体代码,问了一下如果有k个字符串呢？如何找这k个字符串的LCS?

我struggle了一会，就说了一个笨方法：　首先从k个字符串挑一个最短的那个假设为s1，然后拿s1所有的子串和其他字符串进行KMP匹配，那么时间复杂度是`O(k*n^2)`,其实我当时说错了，应该是`O(k*n^3)`

Follow up的情景我觉得应该还有更好的办法，我这个办法是没有办法的办法

####其他
又问了我gdb的用法，说说常用的那些调试命令，怎么产生dump文件，怎么设置条件断点，怎么设置观察断点

又问了我shell脚本，有一个文件里面每行存储ip user query_id三项，然后找出出现次数最多的query_id的所有行． 我很艰难的写了 query_id = cat file | awk '{ print $3} | sort | awk '{ ...}''; cat file | '($3 == $query_id){ print $0}', 面试官说我写的复杂了...



总结:
我觉得算法方面还是需要多做题，因为还是问到了我之前没做过的问题，另外gdb, shell, git这些我在简历上写的东西真的需要好好练练!!!每次都被问到