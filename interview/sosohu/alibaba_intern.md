```C++
一面:

问: 先是拿着我的简历看了一下问我是考研还是保研到计算所的?
我说:保研

接着问这些项目经历中你最引以为豪,拿得出手的介绍下?
心里: 我擦,这不是和吴博雅被问到的一样的么,还好有准备过
我说: 最拿得出手的就是在Intel实习时期的高性能并行程序的优化,这个东西之初我一点也不懂,
通过不断的看它们的资料慢慢学习怎么优化,其中不得不提就是Intel的性能分析工具很厉害,
帮了我很大的忙,就比如说分析到了除法很慢的瓶颈,然后我就展开优化.
问: 那是怎么优化除法的?
我说: 通过以乘法代替除法用来减少除法,在纸上举了一个例子a/c, b/d转为e=1.0/(c*d), 
a*d*e,b*c*e这样子,不过这个方法有精度损失的问题,但是我们和客户沟通,他们说没事.
我说: 另外就是分析出向量化程度不够等情况,然后按照Intel的相关资料,调整代码,提高向量化
程度
他说: 所以你的项目简单来说就是用人家的工具找优化点然后优化?
心理: 汗,这样说的感觉好水...
我说: 虽然从结果上看是这样的,但是优化这个过程有很多路,只有一些正确的路,很多优化方法都
效果很一般,所以这个过程还是很复杂的...
他问: 另外,我看简历上这个项目标着MapReduce,这是怎么回事?
我说: 那是另一个项目,不是这个,Intel基于MIC开发的MapReduce框架
他问: 那你简单说说MapReduce过程?
我说: 我就画图简单说了Map, Shift, Reduce阶段,说的很简单,本以为他还是审问,没想到就
不问了.
总结: 觉得他对我的这个项目不是很了解,兴趣也并不大

问: 你这里说你熟悉GDB,你平时是分析dumpcore还是单步调试?
我说: 单步调试
问: 那么你知道gdb中被调函数中想打印上层函数局部变量怎么打印么?
我说: 不知道....我没用过
问: 那多线程调试时候,怎么切换到另外的线程呢?
我说: info thread, thread thread_id
还问了一个什么,我不太记得了,反正我没回答出来...
问: 看来你gdb用的不是很深啊...
我: ...
问: 还有你说你熟悉git, 那么怎么远程添加分支?
我: 不知道...
问: 那你平时用一些啥命令?
我: git init, git add , git commit ...
问: 哦哦,你平时大多本地开发呀
我: 对,远程开发也只有和同学一起在github上合作
总结: 觉得这部分回答的很糟,感觉自己坑了自己啊,没想到这玩意还问

问: 给你个函数f(int a, char b, double c){}然后main函数中调用f(1, 'a', 1.0)那么
画一下这个调用过程中栈的变化...
心理: 编译原理...
我说: 我在图上大致画了一下.
他说: 你具体标注一下每一块的地址空间大小
我说: 首先压栈三个参数,然后填一个貌似4字节的地址用来传返回值...
他说: 那么具体写写三个参数的地址
我说: 第一个参数1,占4个字节,接着'a'一个字节,然后空3个,8字节对齐,接着是1.0
(其实这说的很不对,,)
总结: 这个我虽然看过很多次,但是具体起来还是不太清楚,回答的也是很多错误.

问: 字符串匹配都有哪些算法?
我说: KMP还有简单粗暴的O(nm)算法,本想说BM的但是不懂怕坑
问: 那KMP算法你能简单说一下么?
我说:  KMP最难的就是求跳转数组,这个跳转数组实质就是最长前后缀...我就大致
举例画了一下,但是具体代码是写不出的,很怕他让我写代码...
他说: 那行,你就实现一个简单版本的字符串匹配,要求找到所有匹配位置,目的是要
好用...
我说: 我就开始写了一个简单的: bool strMatch(const string &, const string &, 
vector<int> result)...
他说: 不行,你这个C程序怎么用啊?
心理: 汗......这不是C/C++工程师么,STL都不行...
我说: 那改成int strMatch(const char* , const char* , int*& result),
这里result指针可以是用户提前申请好空间,
但是这样不太好
他说: 那不行,用户怎么知道该申请多大空间呢
我说: 那我可以申请,但是这样用户负责delete
他说: 这可以,这完全接受
我说: 于是我就简单的写了带有malloc和realloc的函数,不过realloc我还用错了
他说: 这个realloc是什么?
我说: 库函数啊
他说: 哪有这个
心理: 汗...
他说: 我查查,于是他在电脑查了一下,然后说假设没有你怎么做?
我说: 重新malloc然后拷贝过去
他说: 拷贝过去之后呢?
我说: 释放以前的
他说: 那你这代码有bug
我说: 我看一下,然后发现确实有bug....改了一下
他说: 还有bug
我说: 怎么会,我看一下,然后啊....确实有bug,汗,改了一下....
总结: 这么简单的算法代码还好几个bug真是汗颜...

他说: 你有什么要问我的么?
我说: 你们实习生培养计划是怎样的?
他说: 这个各部门不一样,主要还是自己学习
我说: 对对,你们也挺忙的,那您是哪个部门的呢?
他说: 杭州阿里云
我说: 听说北京也有阿里云
他说: 对,杭州北京都有,对了,对于工作地点你有什么要求?
我说: 北京杭州都可以,我是南方人嘛,杭州很喜欢的.
总结: 提问是提前想好的,有点中规中矩吧


总结:其实每个点都暴露很多问题,对了,它还问了C++中全局变量定义在.h文件还是
.cpp文件,我他妈 脑残说了.h.... 现在想想应该把变量作用域,C中的强弱符号好好讲讲,
哪知当时一心想着.cpp里面就用起来很麻烦...编译那块说的不太清楚,算法那部分
没能bug free很遗憾

二面:
二面还是技术面,上来就让我自我介绍一下,我介绍的很简单,只是说了一下本科研究生
在哪里...(感觉还得准备一套自我介绍),然后还是让我自己说一下自己最拿得出手的项目,
于是我又重复说了一面说的那个项目,但是说的比较简略,而且他听完后也没问什么,
而是说我们来做道题吧...

[算法题]
有一个字符串数组设为vector<string> strs, 和另一个字符串数组vector<string> 
prefix,  找出strs中满足含有某个前缀属于prefix的所有字符串.
例如:
vector<string> prefix = {"ab", "cf", "abc"};
vector<string> strs = {"abcddd", "add"};
那么返回vector<string> result = {"abcddd"};
注: 字符串中元素均为小写字母

首先,我和他沟通之后确定了题意,然后第一时间想到了字典树,于是顺着这个思路想到了
初步解法,于是先在纸上和他讲解了一下我的想法,询问他觉得这样如何,他点了点头,
于是我就开始编写代码,整个代码编写大概花了5-10分钟,然后一行一行的讲解,
直到程序结束,然后他说可以.

写完代码后,他问平时有没有做题什么的? 我说我在hihocoder有练习一些编程,然后他就说
那我们再来看一题吧....

[算法题]
在a X b大小的二维网格中,有(X1, X1),...(Yn, Yn)这个n个点,然后从网格中找出一个点,
使得这个点到这个n个点的曼哈顿距离和最小.

这题我之前有想到过,但是没细想=.=,所以只能现场想吧,于是我列出函数:
f(x, y) = |x - X1| + .. + |x - Xn| + |y - Y1| + ... + |y - Yn|
所以可以看出,x和y是无关的,所以可以独立求解,那么就转化为一维的曼哈顿距离问题了.
其实此时我是不知道怎么求一维曼哈顿距离问题的,但是幸运的是面试官一直在纠结为啥
x和y是独立的呢? 我就举了个例子解释,最后终于解释清楚了,
然后他就悻悻然,居然不继续问咋分别求x和y了....我就借坡下驴,就没再说话,
然后就结束了.........

后来回去和大师讨论发现,原来一维曼哈顿最小距离和问题就是这些X1,...,Xn的中位数,
具体证明也很简单,使用递推和反证法就可以了.

接着问了网络中如何进行拥塞避免的?
我说采用慢启动和拥塞避免两个阶段,当网络发生拥塞时候,拥塞窗口从1,2,4这样指数增加
到一定值后转到拥塞避免阶段,此时拥塞窗口的大小就是线性的增加. 数据大小为拥塞窗口
和滑动窗口中的最小值.

总结:	二面面试官感觉对我的项目不是很感兴趣,所以就直接上题.....索性这两题还不是很难,
另外,他对代码的bug似乎不在意,不像一面面试官那样,对于那个字典树问题,我应该向他解释
一下时间和空间复杂度的,不过他也没问,感觉给我的push感并不是很大.

三面:
三面还是一个工程师,还是先让我自我介绍,然后说一个最牛逼的项目,我还是故技重施说那个
项目......这个面试官问项目问的比较深,比如怎么优化的? 有哪些方面? 说完项目,问了一下C++, 
指针和引用的区别? 多态怎么实现的? 我画了一下虚函数表,他居然问这种设计从CPU角度考虑
有什么问题,我尼玛就晕了, 没见过这么问的....我就瞎扯PC会跳转,带来流水线重刷,数据局部性
丢失等......然后问,那你能不能重新设计一下多态的实现? 我觉得他一定实在逗我,我说不会..

还问,在实验室做什么? 我们组有多少人,我的贡献有多少? 实验室中最敬佩谁? 有没有看过什么
开源代码? 平时关注一些什么技术? 对什么新技术比较了解?

总结:	三面大部分时间在问项目,觉得还是比较平稳的,关于CPU那个真的让我摸不着头脑


hr面:
先让我在纸上画一颗自己心目中的树.(真正的树,不是红黑树,二叉树...)
问我平时学习时间多还是其他事时间多?
问我为啥读研以来都没获奖过?
让我描述一下我的一个RoboGame比赛的情况,小组分工,自己作为什么角色?
Intel实习给你最大的感觉是什么?  我说自由,然后吐槽了一下我们实验室....(觉得这样不太好)
未来的规划?
实习地点和未来工作地点?
```