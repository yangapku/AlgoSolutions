| 题目                                 | 基本思想                                                                                                                                                                                                                                        | 分类                             |
|--------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------|
|[面积最大的全1子矩阵](http://ac.jobdu.com/problem.php?pid=1497) | 枚举右下角的位置，从右到左扫描，不断更新最大面积，复杂度O(N^3)，又加了一点剪纸，基本卡时限AC，通过枚举瓶颈边，可以实现O(N^2)的时间复杂度，类似于leetcode中求直方图最大面积的题目                                                                | 枚举                             |
|[项目安排](http://ac.jobdu.com/problem.php?pid=1499) | 一个非常类似的题目是要求完成尽可能多的项目数，可以采用贪心完成。添加报酬之后，对于每一个项目，要么不做，此时最优值就是前一个项目截止时间所对应的最优值；要么做该项目，最优值是该项目的报酬加上在这一项目开始时间的最优报酬，动态规划O(nlgn)可解 | 动态规划                         |
|[最大值最小化](http://ac.jobdu.com/problem.php?pid=1502) | 二分搜索，对于每一个可能的值，通过贪心策略进行验证即可                                                                                                                                                                                          | 二分；贪心                       |
|[寻找表达式](http://ac.jobdu.com/problem.php?pid=1498) | 暴力枚举每一种可能的情形，最后3^14的大数据挂了，于是耍流氓打表了……                                                                                                                                                                              | 枚举，递归                       |
|[狼抓兔子](http://www.lydsy.com/JudgeOnline/problem.php?id=1001) | 题目要求图的最小割，但数据范围过大，用通常的算法求最小割会超时+超内存；平面图的最小割问题可以转化为对偶图的最短路问题，通过重构图，用spfa算法求最短路即可。                                                                                     | spfa最短路；平面图最小割         |
|[轮状病毒](http://www.lydsy.com/JudgeOnline/problem.php?id=1002) | 至今未想清楚递推公式究竟是怎么来的。。。                                                                                                                                                                                                        | 大整数；递推；生成树计数         |
|[物流运输](http://www.lydsy.com/JudgeOnline/problem.php?id=1003) | 对于每一天，枚举前面第一个发生路线变化的节点，进行状态转移，dp(n)=dp(j)+cost(j+1,n)*(n-j)+K,最后需要减掉一个多余的K，cost数组可以通过最短路算法预先计算出来                                                                                     | 动态规划；最短路                 |
|[越狱](http://www.lydsy.com/JudgeOnline/problem.php?id=1008) | 快速幂加上简单的组合数学                                                                                                                                                                                                                        | 组合数学                         |
|[Cards](http://www.lydsy.com/JudgeOnline/problem.php?id=1004) | 利用Polya定理来进行计数，分别考虑每一个置换，对每一个置换而言，同一个置换组中的节点必须被染成相同的染色，由于题目中对颜色之和做了限制，还需要结合动态规划求解方案数；最后，在模域除以一个数，需要乘以该数的逆元。                               | 组合数学；动态规划；快速幂       |
|[二进制中1的个数](http://ac.jobdu.com/problem.php?pid=1513) | __builtin_popcount搞定                                                                                                                                                                                                                          | 水                               |
|[把数组排成最小数](http://ac.jobdu.com/problem.php?pid=1504) | 不能简单按照字典序，注意一个字符串为另一个字符串前缀的情形                                                                                                                                                                                      | 排序                             |
|[明明的烦恼](http://www.lydsy.com/JudgeOnline/problem.php?id=1005) | 生成树计数的问题，根据prufer编码（第一次听说这种东西……），有标记的生成树跟一个长度为n-2的序列是一一对应的，因此生成树计数就转化成了组合计数的问题，首先选出有度数限制的顶点，然后根据多项式系数求解。由于涉及高精度运算，python是比较好的选择   | 生成树计数；组合数学；高精度     |
|[水平可见直线](http://www.lydsy.com/JudgeOnline/problem.php?id=1007) | 注意分析一条直线在什么情况下会被掩盖，将直线按照斜率升序排列，用栈来维护，每遇到一条直线，就从栈中取出两条直线计算交点，如该直线在交点以上，则将原来的直线覆盖，反之则没有覆盖，同时还需注意两条直线斜率相同的情形。                            | 栈；排序；几何                   |
|[神奇的国度](http://www.lydsy.com/JudgeOnline/problem.php?id=1006) | graph coloring在一般情况下是NP问题，但对于弦图有多项式算法。于是，先找出弦图中的完美消除序列，在逆向进行标记染色。第一次做和弦图相关的题目，长见识……                                                                                            | 弦图；图颜色；最大势算法         |
|[玩具装箱](http://www.lydsy.com/JudgeOnline/problem.php?id=1010) | 朴素的动态规划复杂度为O(N^2)，会超时；注意到决策具有单调性，于是可以二分更新决策区间，用双端队列来进行维护。神题啊……折腾了一天……                                                                                                                | 动态规划；双端队列；二分         |
|[最大数](http://www.lydsy.com/JudgeOnline/problem.php?id=1012) | 维护一个单调下降的队列，每次查询采用二分查找                                                                                                                                                                                                    | 单调队列；二分                   |
|[GT考试](http://www.lydsy.com/JudgeOnline/problem.php?id=1009) | 定义状态f(i, j)为长度为i的字符串最后j个字符为模板的前j个字符，f(i+1, j)和f(i, j)之间可以构造一个固定的转移矩阵，不管i的取值是多少，于是可以利用矩阵的快速幂来进行求解                                                                           | 动态规划；矩阵快速幂；字符串计数 |
|[最长上升子序列](http://ac.jobdu.com/problem.php?pid=1533) | 最长上升子序列可以通过O(N^2)的动态规划算法求解，但事实上还有O(nlgn)的解法，可以借助于二分查找实现，不过用stl里面的set更方便                                                                                                                     | 动态规划                         |
|[Spheres](https://www.hackerrank.com/contests/infinitum-jun14/challenges/spheres) | 首先利用物理上的相对运动把加速度归约到一个球上（高中物理没白学啊……），然后列出时间t时的距离函数，通过对t求导最小化该函数得到两个球的最近距离，如果该距离小于两球的半径之和，则说明会碰撞，反之则不会发生碰撞。                                  | 几何；求最值                     |
|[星球大战](http://www.lydsy.com/JudgeOnline/problem.php?id=1015) | 逆向思考，于是原问题转化为不断向图中加边和顶点，快速求出连通分量数目的问题，并查集可解。同时，由于顶点的数目较多，采用前向星表示更为高效，计数排序可以实现边的线性时间排序。                                                                    | 并查集；图论；前向星             |
|[最小生成树计数](http://www.lydsy.com/JudgeOnline/problem.php?id=1016) | 要求对最小生成树的选边过程有一个比较深刻的了解，不同最小生成树的边权集合是相同的，只是对于特定长度的边，选哪些组合并不确定。用位运算枚举，根据乘法原理可解。                                                                                    | 最小生成树；并查集；位运算       |
|[球形空间产生器](http://www.lydsy.com/JudgeOnline/problem.php?id=1013) | 根据球心定义，可以列出n个独立的方程，其中的平方项相互抵消，变成了一个线性方程，高斯消元法求解。                                                                                                                                                 | 几何；高斯消元法                 |
|[How many integers can you find](http://acm.hdu.edu.cn/showproblem.php?pid=1796) | 原子集合定义：可以被第i个数整除的数的个数；利用容斥原理可解，枚举是借助于位运算比较方便，当然，深搜也是可以的。                                                                                                                                 | 容斥原理；位运算                 |
|[逃生](http://bestcoder.hdu.edu.cn/contests/contest_showproblem.php?pid=1001&cid=525) | 赤裸裸的拓扑排序，但是要注意字典序的问题，因此需要按照编号从大到小枚举                                                                                                                                                                          | 拓扑排序                         |
|[DZY Loves Sequences](http://codeforces.com/problemset/problem/446/A) | 枚举将要被改变的那个数字的位置，把它之前的最长上升序列和之后的最长上升序列拼接起来即可，需要注意边界条件。                                                                                                                                      | 枚举                             |
|[DZY Loves Modification](http://codeforces.com/problemset/problem/446/B) | 通过简单证明可知，行和列之间的操作顺序是可以交换的，因此可以枚举有i个行操作，剩余的均为列操作，对于所有的行操作而言，显然要遵循贪心的选择过程，为了提高时间效率，可以用堆来进行维护。                                                           | 贪心；最大堆                     |
|[Jzzhu and Cities](http://codeforces.com/problemset/problem/449/B) | 单源最短路径的改编版本，在一个图中，为了维持到一个顶点的最短距离保持不变，事实上只需要n-1条边，对应于Dijkstra算法中每个顶点最后被更新的边；同时为了提高时间效率，同样需要维护堆，否则O(N^2)会超时                                               | 单源最短路径；堆                 |
|[Jzzhu and Chocolate](http://codeforces.com/problemset/problem/449/A) | 假设在列上切了i刀，不难列出相应的最小面积表达式，为了最大化最小面积，只需要取两个边界值即可                                                                                                                                                     | 贪心                             |
|[Jzzhu and Apples](http://codeforces.com/problemset/problem/449/C) | 枚举每一个素数，它只能是与其倍数构成pair，如果这样的数共有偶数个，可以全部匹配，如果是奇数个，则需要剔除一个，将其放到最后的一个公共空间里，因此剔除2*p最合适                                                                                   | 构造性算法                       |
|[K尾相等数](http://acm.nyist.edu.cn/JudgeOnline/problem.php?pid=212) | 两个幂次对1000取模的结果应该相同，一旦碰到重复的结果以后就会不断重复，因此不断增加幂指数直到出现环                                                                                                                                              | 数论                             |
|[InvariantSets](TopCoder SRM 628 div2 1000) | 注意到一个环中的点，要么全选，要么全不选，因此可以缩点将原图转化为一个森林，然后再对每棵树利用动态规划计数                                                                                                                                      | 图论；组合计数；组合数学         |
|[BishopMove](TopCoder SRM 628 div2 250) | 很经典的小题目，嗯……奇偶性不同则不可达，在同一条对角线上则一步可达，否则需要两步                                                                                                                                                                | 观察规律……                       |
|[BracketExpressions](TopCoder SRM 628 div2 500) | 题目的数据规模较小，可暴力枚举，对于每一种情况，用栈来验证是否符合格式要求                                                                                                                                                                      | 栈；枚举                         |
|[受欢迎的牛](http://www.lydsy.com/JudgeOnline/problem.php?id=1051) | 一个有向图可以分成若干个强连通分量，其中至少有一个强连通分量无出边，如果这样的SCC数目大于1，则无解，等于1时进行计数即可，SCC的求解可以通过两次dfs，第一次求定点的拓扑序，第二次dfs求每个scc对应的编号                                           | 图论；强连通分量                 |
|[猴子舞](http://soj.me/show_problem.php?pid=1297) | 抽象成数学问题，就是将N进行分解，并且得到的数的lcm最大，i分成j个圈作为状态，可以很自然看出动态规划的特点                                                                                                                                        | 数论；动态规划                   |
|[大众比萨](http://acm.sdibt.edu.cn/JudgeOnline/problem.php?id=1133) | 经典的NP问题：可满足性问题。只能通过暴力求解，借助于位运算可以提高检验的效率                                                                                                                                                                    | 枚举；位运算                     |
|[点在哪](http://acm.sdibt.edu.cn/JudgeOnline/problem.php?id=1404) | 水……鬼都会做                                                                                                                                                                                                                                    | 几何                             |
|[DivisorsPower](TopCoder SRM 628 div1 250) | 注意到枚举n是没有希望的，而且也没有任何单调性能够让算法加速。但是可以枚举指数项，对于确定的幂指数，n可以通过二分确定，然后再通过因式分解判断是否合法                                                                                            | 二分；枚举                       |
|[CircuitsConstruction](TopCoder SRM 628 div1 500) | 题目所给的其实就是波兰表达式，要想最大化结果，只需要最大化一个运算符所覆盖的项数，这可以通过树的分治完成                                                                                                                                        | 递归；树形动态规划               |
|[GravityBomb](TopCoder SRM 200 div2 500) | 统计一下每列的X字符数目，取最小值，并进行消除                                                                                                                                                                                                   | 水题                             |
|[WindowManager](TopCoder SRM 200 div2 900) | 模拟即可，但情况数目比较多，需要细心一点                                                                                                                                                                                                        | 水题                             |
|[FindPoint](https://www.hackerrank.com/challenges/find-point) | 对称点，不多说。。                                                                                                                                                                                                                              | 水题                             |
|[SherlockAndPlanes](https://www.hackerrank.com/challenges/sherlock-and-planes) | 判断四点是否共面，只需要看三个向量所构成的立体图形的体积是否为零，可通过一次叉积和一次点积完成                                                                                                                                                  | 几何                             |
|[Spheres](https://www.hackerrank.com/challenges/spheres) | 转化为相对运动，然后借助于叉积求出点到直线的最短距离，需要注意相对运动的方向是否是背离的方向，通过点积判断角度是否是钝角即可                                                                                                                    | 几何                             |
|[志愿者招募](http://www.lydsy.com/JudgeOnline/problem.php?id=1061) | 列出每一天所要满足的约束方程，相邻方程相减可以保证每个变量出现两次，于是把方程作为顶点，进行构图，求出最小费用最大流                                                                                                                            | 最小费用最大流；图论；神题       |
|[Windy数](http://www.lydsy.com/JudgeOnline/problem.php?id=1026) | 进行动态规划，但是边界情况比较多，需要仔细设计状态以及状态之间的转移                                                                                                                                                                            | 动态规划                         |
|[矩阵游戏](http://www.lydsy.com/JudgeOnline/problem.php?id=1059) | 首先观察到同一行或者同一列的元素是不可能同时对最终结果产生贡献的，并且如果两个点的横纵坐标都不相同，一定可以都对最终结果产生贡献。于是需要找到n个点，任意两个点的横纵坐标均不相同，“互斥”的特点刚好符合二分图的性质，匈牙利算法求解             | 二分图匹配；深度搜索；匈牙利算法 |
|[修车](http://www.lydsy.com/JudgeOnline/problem.php?id=1070) | 将每个技术人员节点分裂成n个，每个表示倒数第几个修车，构图，求最小费用流                                                                                                                                                                         | 最小费用流；图论                 |
|[Courses](http://poj.org/problem?id=1469) | 二分图匹配，不多说。。                                                                                                                                                                                                                          | 二分图匹配                       |
|[树的最小高度](http://ac.jobdu.com/problem.php?pid=1536) | 问题的本质是求解树的直径，第一次广搜可以得到边界上的点，第二次广搜的结束点得到另一个边界上的点，最小高度就是半径的一半                                                                                                                          | 图论；广搜                       |
|[重叠的最长子串](http://ac.jobdu.com/problem.php?pid=1535) | Rabin-Karp绝对是神算法啊，搞个hash线性时间就可以完成字符串匹配，以后碰到字符串匹配的题目就都用它了。                                                                                                                                            | 字符串匹配                       |
|[买卖股票](http://ac.jobdu.com/problem.php?pid=1537) | 动态规划，不多说。。。                                                                                                                                                                                                                          | 动态规划                         |
|[数组中第K小的数](http://ac.jobdu.com/problem.php?pid=1534) | 很聪明的二分查找，对目标数字K进行二分，每次线性时间可以统计出小于等于K的数字的个数，然后决定走左分支还是右分支                                                                                                                                  | 二分查找                         |
|[Find The Shortest Common Superstring](http://acm.hdu.edu.cn/showproblem.php?pid=1841) | 和九度上的题目如出一辙，换了一个KMP匹配的解法，关键在于明白KMP算法在匹配失败时，指向模式串的指针恰好对应于最长的前缀。                                                                                                                          | KMP                              |
|[建筑抢修](http://www.lydsy.com/JudgeOnline/problem.php?id=1029) | 按照截止时间进行排序，然后依次选择，如果不能选的话，想办法减小当前所用的时间，可用堆来高效实现                                                                                                                                                  | 贪心；最小堆                     |
|[Boredom](http://codeforces.com/problemset/problem/455/A) | 居然是用动态规划，一开始以为有多复杂，还是自己的状态定义有问题                                                                                                                                                                                  | 动态规划                         |
|[小约翰逊的游戏John](http://www.lydsy.com/JudgeOnline/problem.php?id=1022) | 普通Nim游戏的简单变形，取到最后一个算赢改成了算输。只需要对单个石子堆的情况进行特殊分析即可。                                                                                                                                                   | 博弈                             |
|[生日快乐](http://www.lydsy.com/JudgeOnline/problem.php?id=1024) | 和棋盘分割的问题比较相似，分别考虑横向和纵向的情形，递归求解。                                                                                                                                                                                  | 递归                             |
|[糖果传递](http://www.lydsy.com/JudgeOnline/problem.php?id=1045) | 纯数学问题，列出代价函数，规约为最小化一系列绝对值之和的问题，只需要取各个常数项的中位数。                                                                                                                                                      | 数学                             |
|[互不侵犯King](http://www.lydsy.com/JudgeOnline/problem.php?id=1087) | 暴力枚举显然要挂，需要以行为状态进行状态转移，用位操作来表示各个状态之间的相容性                                                                                                                                                                | 基于状态压缩的动态规划           |
|[扫雷Mine](http://www.lydsy.com/JudgeOnline/problem.php?id=1088) | 关键在于注意到，每个格子只影响到相邻的三行，因此可以以行为状态进行转移，另外还需要记录当前行和下一行的雷放置情况                                                                                                                                | 动态规划                         |
|[圆上的整点](http://www.lydsy.com/JudgeOnline/problem.php?id=1041) | 神题啊……需要对勾股数有比较好的理解                                                                                                                                                                                                              | 数学；几何                       |
|[硬币购物](http://www.lydsy.com/JudgeOnline/problem.php?id=1042) | 神题……先考虑没有数目限制情形下的方案，再根据数目上的限制采用容斥原理删除不符合要求的方案                                                                                                                                                        | 动态规划；容斥原理               |
|[鬼谷子的钱袋](http://www.lydsy.com/JudgeOnline/problem.php?id=1192) | 构造出最优的策略，也就是以2为倍数递增选数，直至剩余的钱数少于要选的金币数目                                                                                                                                                                     | 水题                             |
|[字符串加密cipher](http://www.lydsy.com/JudgeOnline/problem.php?id=1031) | 赤裸裸的后缀数组，求出所有字符串后缀的rank数组来，再花费线性时间便可以求得目标字符串                                                                                                                                                            | 字符串后缀数组                   |
|[理想的正方形](http://www.lydsy.com/JudgeOnline/problem.php?id=1047) | 和sliding window挺像的，利用决策单调性进行预计算，得到一个二维范围内的最值，然后再平方时间扫描得到结果                                                                                                                                          | 决策单调性                       |
|[蜥蜴](http://www.lydsy.com/JudgeOnline/problem.php?id=1066) | “每次跳跃都会使高度减一”具有流网络的特征，因此对矩阵构建一个流网络，每个顶点一分为二，求解流网络的最大流                                                                                                                                        | 网络流；图论                     |
|[排列perm](http://www.lydsy.com/JudgeOnline/problem.php?id=1072) | 看到字符串长度只有10，显然暴力枚举……                                                                                                                                                                                                            | 枚举                             |
|[移动玩具](http://www.lydsy.com/JudgeOnline/problem.php?id=1054) | 把棋盘压缩成一个16位的整数，进行广度优先搜索即可                                                                                                                                                                                                | 广搜                             |
|[反素数](http://www.lydsy.com/JudgeOnline/problem.php?id=1053) | 列出素数表来，对每个素数可取的个数进行递归搜索即可，注意边界上的结果更新以及恰当剪枝                                                                                                                                                            | 数论；递归                       |
|[2月29日](http://hihocoder.com/problemset/problem/1148) | 用容斥原理随便搞搞就行了。。 | 数学 |
|[回文字符序列](http://hihocoder.com/problemset/problem/1149) | 和公共子序列计数本质上是一样的，分最开头的字母是否相等两种情况，注意减掉重复计算的部分 | 动态规划；组合计数 |
|[基站选址](http://hihocoder.com/problemset/problem/1150) | 首先两个坐标是互相独立的，然后把优化目标写出来，发现最优解就在用户的质心处，扫描小范围内的整数点网格可解。有人搞模拟退火，什么鬼。。 | 优化 |
|[彩色的树](http://hihocoder.com/problemset/problem/1156) | 很感人的一道题。。。就是如何高效维护树中的信息，每个节点只维护子节点信息，就可以实现O(1)查询和O(1)更新了 | 树 |
|[攻城略地](http://hihocoder.com/problemset/problem/1160) | 每个连通分量，只需要选择权重最小的顶点，并且一个连通分量删掉不影响连通性的多余边不会影响最终结果；如果还不够，就把其余顶点排序，从小到大选。。 | 图论 连通分量 |
|[质数相关](http://hihocoder.com/problemset/problem/1158) | 二部图最大独立点集，我太渣了。。。建立二部图，做最大匹配，总数减掉最大匹配的一半就是答案 | 二部图； 独立点集 |
|[Girls and Boys](poj.org/problem?id=1466) | 还是二部图最大独立点集，嗯。。 | 二部图 |
|[扑克牌](http://hihocoder.com/problemset/problem/1159) | 组合dp，感人肺腑不能多说。。 | 组合计数；动态规划 |
|[Cutting Banner](http://codeforces.com/problemset/problem/538/A) | 表述不清，第一次被别人成功hack，超级不爽。。 | 暴力枚举 |
|[Quasi Binary](http://codeforces.com/problemset/problem/538/B) | 对每一个非零位进行贪心构造，直到变成0 | 贪心 |
|[Tourist's Notes](http://codeforces.com/problemset/problem/538/C) | 水题不想多说。。 | 贪心 |
|[Weird Chess](http://codeforces.com/problemset/problem/538/D) | 看上去很难，其实就是根据约束条件不断删除候选解 | 构造算法 |
|[Demiurges Play Again](http://codeforces.com/problemset/problem/538/E) | 博弈论相关，当轮到对手时，要选择所有可能的路径最优解中的最差解；当轮到自己时，选择所有可能路径中最优解的最优解，大概就是这样，比较绕。。 | 博弈论 |
|[A Heap of Heaps](http://codeforces.com/contest/538/problem/F) | 枚举显然超时，关键点在于一个节点的父节点只可能有平方根量级个，区间和维护的时候不要挨个更新，只更新两端，最后累加。 | 数学 数据结构 |
|[Remmarguts' Date](http://poj.org/problem?id=2449) | 第一次写K短路，弱菜。。和最短路的A Star算法类似，只是把第K次出优先队列的值作为结果 | 图论； A Star |
|[Combination Lock](http://codeforces.com/problemset/problem/540/A) | 水题不多说。。 | 水 |
|[School Marks](http://codeforces.com/problemset/problem/540/B) | 贪心构造，满足中位数要求就不断填充临界值，一旦满足就只放最低分 | 贪心 |
|[Ice Cave](http://codeforces.com/problemset/problem/540/C) | 很不错的小题目，我智商太低。。关键是从一个完整点出发，只要相邻的有一个完整点，就可以回到原点，边界情况比较多 | 广度搜索；考智商 |
|[Bad Luck Island](http://codeforces.com/problemset/problem/540/D) | 感觉跟AI里面的markov decision process很像啊。。根据前一步的概率分布去计算下一步的概率分布直到稳定状态 | 概率；动态规划 |
|[Infinite Inversions](http://codeforces.com/problemset/problem/540/E) | 归并排序可以用来高效计算逆序数，但是这里序列无限长，所以只能分别计算更改部分的逆序数，和未更改的逆序数，最后加起来 | 分治法 |
|[Ultra-QuickSort](http://poj.org/problem?id=2299) | 经典的计算逆序数，不过刚知道原来还可以用树状数组搞，离散化的基本思想 | 树状数组 |