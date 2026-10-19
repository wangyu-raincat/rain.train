# C++ 算法笔记（LeetCode + ACM）

## 0. 推荐资料

- [OI Wiki](https://oi-wiki.org/)：中文竞赛百科，最全
- [cp-algorithms](https://cp-algorithms.com/)：英文经典算法详解
- [labuladong 的算法笔记](https://labuladong.online/algo/)：LeetCode 套路总结
- [代码随想录](https://programmercarl.com/)：LeetCode 刷题路线
- [Codeforces](https://codeforces.com/) / [AtCoder](https://atcoder.jp/) / [洛谷](https://www.luogu.com.cn/)：ACM 训练
- [LeetCode 中国](https://leetcode.cn/)

## 1. 竞赛模板头

```cpp
#include <bits/stdc++.h>
using namespace std;
using ll = long long;
int main(){
    ios::sync_with_stdio(false); cin.tie(nullptr);
    int T; cin >> T;
    while(T--){ /* solve */ }
}
```

要点：`long long` 防溢出；`1e9+7` 取模；`endl` 换成 `'\n'`。

### 题目（由易到难）

- [509. 斐波那契数](https://leetcode.cn/problems/fibonacci-number/)（简单）
- [50. Pow(x, n)](https://leetcode.cn/problems/powx-n/)（中等）
- [372. 超级次方](https://leetcode.cn/problems/super-pow/)（中等）
- [1922. 统计好数字的数目](https://leetcode.cn/problems/count-good-numbers/)（中等）

## 2. STL 常用

- `vector`, `deque`, `priority_queue<int, vector<int>, greater<int>>`（小根堆）
- `set/map`（有序，O(log n)），`unordered_map`（哈希，ACM 注意被卡）
- `sort`, `lower_bound`, `upper_bound`, `next_permutation`, `__builtin_popcount`

### 题目（由易到难）

- [1. 两数之和](https://leetcode.cn/problems/two-sum/)（简单）
- [217. 存在重复元素](https://leetcode.cn/problems/contains-duplicate/)（简单）
- [242. 有效的字母异位词](https://leetcode.cn/problems/valid-anagram/)（简单）
- [49. 字母异位词分组](https://leetcode.cn/problems/group-anagrams/)（中等）
- [215. 数组中的第K个最大元素](https://leetcode.cn/problems/kth-largest-element-in-an-array/)（中等）
- [347. 前 K 个高频元素](https://leetcode.cn/problems/top-k-frequent-elements/)（中等）
- [23. 合并 K 个升序链表](https://leetcode.cn/problems/merge-k-sorted-lists/)（困难）

## 3. 二分

```cpp
// 找第一个 >= x 的位置
int l = 0, r = n;
while(l < r){ int m = (l + r) / 2; if(a[m] >= x) r = m; else l = m + 1; }
```

二分答案：答案有单调性时，二分答案 + check 函数。

### 题目（由易到难）

- [704. 二分查找](https://leetcode.cn/problems/binary-search/)（简单）
- [35. 搜索插入位置](https://leetcode.cn/problems/search-insert-position/)（简单）
- [34. 在排序数组中查找元素的第一个和最后一个位置](https://leetcode.cn/problems/find-first-and-last-position-of-element-in-sorted-array/)（中等）
- [33. 搜索旋转排序数组](https://leetcode.cn/problems/search-in-rotated-sorted-array/)（中等）
- [162. 寻找峰值](https://leetcode.cn/problems/find-peak-element/)（中等）
- [875. 爱吃香蕉的珂珂](https://leetcode.cn/problems/koko-eating-bananas/)（中等）
- [4. 寻找两个正序数组的中位数](https://leetcode.cn/problems/median-of-two-sorted-arrays/)（困难）
- [410. 分割数组的最大值](https://leetcode.cn/problems/split-array-largest-sum/)（困难）

## 4. 双指针 / 滑动窗口

```cpp
for(int r = 0, l = 0; r < n; r++){
    add(a[r]);
    while(!valid()) remove(a[l++]);
    ans = max(ans, r - l + 1);
}
```

### 题目（由易到难）

- [283. 移动零](https://leetcode.cn/problems/move-zeroes/)（简单）
- [125. 验证回文串](https://leetcode.cn/problems/valid-palindrome/)（简单）
- [11. 盛最多水的容器](https://leetcode.cn/problems/container-with-most-water/)（中等）
- [15. 三数之和](https://leetcode.cn/problems/3sum/)（中等）
- [209. 长度最小的子数组](https://leetcode.cn/problems/minimum-size-subarray-sum/)（中等）
- [3. 无重复字符的最长子串](https://leetcode.cn/problems/longest-substring-without-repeating-characters/)（中等）
- [42. 接雨水](https://leetcode.cn/problems/trapping-rain-water/)（困难）
- [76. 最小覆盖子串](https://leetcode.cn/problems/minimum-window-substring/)（困难）

## 5. 前缀和 / 差分

- 一维前缀和：`s[i] = s[i-1] + a[i]`，区间和 `s[r] - s[l-1]`
- 差分：区间 [l,r] 加 v：`d[l] += v; d[r+1] -= v;`
- 二维前缀和：`s[i][j] = s[i-1][j] + s[i][j-1] - s[i-1][j-1] + a[i][j]`

### 题目（由易到难）

- [1480. 一维数组的动态和](https://leetcode.cn/problems/running-sum-of-1d-array/)（简单）
- [303. 区域和检索 - 数组不可变](https://leetcode.cn/problems/range-sum-query-immutable/)（简单）
- [560. 和为 K 的子数组](https://leetcode.cn/problems/subarray-sum-equals-k/)（中等）
- [238. 除了自身以外数组的乘积](https://leetcode.cn/problems/product-of-array-except-self/)（中等）
- [304. 二维区域和检索 - 矩阵不可变](https://leetcode.cn/problems/range-sum-query-2d-immutable/)（中等）
- [1094. 拼车](https://leetcode.cn/problems/car-pooling/)（中等）
- [1109. 航班预订统计](https://leetcode.cn/problems/corporate-flight-bookings/)（中等）
- [862. 和至少为 K 的最短子数组](https://leetcode.cn/problems/shortest-subarray-with-sum-at-least-k/)（困难）

## 6. 单调栈 / 单调队列

```cpp
stack<int> st; // 下一个更大元素
for(int i = 0; i < n; i++){
    while(!st.empty() && a[st.top()] < a[i]){ nxt[st.top()] = i; st.pop(); }
    st.push(i);
}
```

单调队列用 `deque` 求滑动窗口最值。

### 题目（由易到难）

- [496. 下一个更大元素 I](https://leetcode.cn/problems/next-greater-element-i/)（简单）
- [739. 每日温度](https://leetcode.cn/problems/daily-temperatures/)（中等）
- [503. 下一个更大元素 II](https://leetcode.cn/problems/next-greater-element-ii/)（中等）
- [42. 接雨水](https://leetcode.cn/problems/trapping-rain-water/)（困难）
- [84. 柱状图中最大的矩形](https://leetcode.cn/problems/largest-rectangle-in-histogram/)（困难）
- [239. 滑动窗口最大值](https://leetcode.cn/problems/sliding-window-maximum/)（困难）

## 7. 搜索

- DFS：回溯（排列、组合、子集），注意剪枝
- BFS：无权图最短路、多源 BFS

```cpp
queue<int> q; q.push(s); dist[s] = 0;
while(!q.empty()){ int u = q.front(); q.pop();
  for(int v : g[u]) if(dist[v] < 0){ dist[v] = dist[u] + 1; q.push(v); } }
```

### 题目（由易到难）

- [104. 二叉树的最大深度](https://leetcode.cn/problems/maximum-depth-of-binary-tree/)（简单）
- [101. 对称二叉树](https://leetcode.cn/problems/symmetric-tree/)（简单）
- [226. 翻转二叉树](https://leetcode.cn/problems/invert-binary-tree/)（简单）
- [78. 子集](https://leetcode.cn/problems/subsets/)（中等）
- [46. 全排列](https://leetcode.cn/problems/permutations/)（中等）
- [39. 组合总和](https://leetcode.cn/problems/combination-sum/)（中等）
- [200. 岛屿数量](https://leetcode.cn/problems/number-of-islands/)（中等）
- [994. 腐烂的橘子](https://leetcode.cn/problems/rotting-oranges/)（中等）
- [79. 单词搜索](https://leetcode.cn/problems/word-search/)（中等）
- [51. N 皇后](https://leetcode.cn/problems/n-queens/)（困难）
- [127. 单词接龙](https://leetcode.cn/problems/word-ladder/)（困难）

## 8. 动态规划

- 线性 DP：LIS（O(n log n) 用 lower_bound）、LCS
- 背包：01 背包倒序枚举容量，完全背包正序

```cpp
for(int i = 0; i < n; i++) for(int j = W; j >= w[i]; j--) dp[j] = max(dp[j], dp[j-w[i]] + v[i]);
```

- 区间 DP、树形 DP、状压 DP、数位 DP（ACM 重点）

### 题目（由易到难）

- [70. 爬楼梯](https://leetcode.cn/problems/climbing-stairs/)（简单）
- [746. 使用最小花费爬楼梯](https://leetcode.cn/problems/min-cost-climbing-stairs/)（简单）
- [198. 打家劫舍](https://leetcode.cn/problems/house-robber/)（中等）
- [62. 不同路径](https://leetcode.cn/problems/unique-paths/)（中等）
- [322. 零钱兑换](https://leetcode.cn/problems/coin-change/)（中等）
- [518. 零钱兑换 II](https://leetcode.cn/problems/coin-change-ii/)（中等）
- [416. 分割等和子集](https://leetcode.cn/problems/partition-equal-subset-sum/)（中等）
- [300. 最长递增子序列](https://leetcode.cn/problems/longest-increasing-subsequence/)（中等）
- [1143. 最长公共子序列](https://leetcode.cn/problems/longest-common-subsequence/)（中等）
- [72. 编辑距离](https://leetcode.cn/problems/edit-distance/)（中等）
- [115. 不同的子序列](https://leetcode.cn/problems/distinct-subsequences/)（困难）
- [312. 戳气球](https://leetcode.cn/problems/burst-balloons/)（困难）

## 9. 图论

- Dijkstra（堆优化）：

```cpp
priority_queue<pair<ll,int>, vector<pair<ll,int>>, greater<>> pq;
dist[s] = 0; pq.push({0, s});
while(!pq.empty()){ auto [d,u] = pq.top(); pq.pop(); if(d > dist[u]) continue;
  for(auto [v,w] : g[u]) if(dist[u] + w < dist[v]){ dist[v] = dist[u] + w; pq.push({dist[v], v}); } }
```

- 并查集：

```cpp
int find(int x){ return p[x] == x ? x : p[x] = find(p[x]); }
```

- 拓扑排序、最小生成树（Kruskal）、Floyd、Tarjan（强连通/割点）、LCA（倍增）

### 题目（由易到难）

- [997. 找到小镇的法官](https://leetcode.cn/problems/find-the-town-judge/)（简单）
- [547. 省份数量](https://leetcode.cn/problems/number-of-provinces/)（中等）
- [684. 冗余连接](https://leetcode.cn/problems/redundant-connection/)（中等）
- [207. 课程表](https://leetcode.cn/problems/course-schedule/)（中等）
- [210. 课程表 II](https://leetcode.cn/problems/course-schedule-ii/)（中等）
- [743. 网络延迟时间](https://leetcode.cn/problems/network-delay-time/)（中等）
- [1584. 连接所有点的最小费用](https://leetcode.cn/problems/min-cost-to-connect-all-points/)（中等）
- [787. K 站中转内最便宜的航班](https://leetcode.cn/problems/cheapest-flights-within-k-stops/)（中等）
- [778. 水位上升的泳池中游泳](https://leetcode.cn/problems/swim-in-rising-water/)（困难）
- [1192. 查找集群内的关键连接](https://leetcode.cn/problems/critical-connections-in-a-network/)（困难）

## 10. 数据结构（ACM 进阶）

- 树状数组：

```cpp
void add(int i, ll v){ for(; i <= n; i += i & -i) t[i] += v; }
ll sum(int i){ ll r = 0; for(; i; i -= i & -i) r += t[i]; return r; }
```

- 线段树（区间修改 + 懒标记）、ST 表、字典树 Trie

### 题目（由易到难）

- [706. 设计哈希映射](https://leetcode.cn/problems/design-hashmap/)（简单）
- [208. 实现 Trie (前缀树)](https://leetcode.cn/problems/implement-trie-prefix-tree/)（中等）
- [307. 区域和检索 - 数组可修改](https://leetcode.cn/problems/range-sum-query-mutable/)（中等）
- [315. 计算右侧小于当前元素的个数](https://leetcode.cn/problems/count-of-smaller-numbers-after-self/)（困难）
- [218. 天际线问题](https://leetcode.cn/problems/the-skyline-problem/)（困难）
- [715. Range 模块](https://leetcode.cn/problems/range-module/)（困难）

## 11. 数学

- 快速幂：

```cpp
ll qpow(ll a, ll b, ll m){ ll r = 1; a %= m; for(; b; b >>= 1, a = a * a % m) if(b & 1) r = r * a % m; return r; }
```

- gcd/lcm、埃氏筛 / 欧拉筛、逆元（费马小定理）、组合数预处理

### 题目（由易到难）

- [9. 回文数](https://leetcode.cn/problems/palindrome-number/)（简单）
- [1071. 字符串的最大公因子](https://leetcode.cn/problems/greatest-common-divisor-of-strings/)（简单）
- [204. 计数质数](https://leetcode.cn/problems/count-primes/)（中等）
- [172. 阶乘后的零](https://leetcode.cn/problems/factorial-trailing-zeroes/)（中等）
- [50. Pow(x, n)](https://leetcode.cn/problems/powx-n/)（中等）
- [372. 超级次方](https://leetcode.cn/problems/super-pow/)（中等）
- [60. 排列序列](https://leetcode.cn/problems/permutation-sequence/)（困难）
- [458. 可怜的小猪](https://leetcode.cn/problems/poor-pigs/)（困难）

## 12. 字符串

- KMP、字符串哈希、Manacher、Trie

### 题目（由易到难）

- [14. 最长公共前缀](https://leetcode.cn/problems/longest-common-prefix/)（简单）
- [459. 重复的子字符串](https://leetcode.cn/problems/repeated-substring-pattern/)（简单）
- [28. 找出字符串中第一个匹配项的下标](https://leetcode.cn/problems/find-the-index-of-the-first-occurrence-in-a-string/)（简单）
- [5. 最长回文子串](https://leetcode.cn/problems/longest-palindromic-substring/)（中等）
- [1392. 最长快乐前缀](https://leetcode.cn/problems/longest-happy-prefix/)（困难）
- [214. 最短回文串](https://leetcode.cn/problems/shortest-palindrome/)（困难）
- [10. 正则表达式匹配](https://leetcode.cn/problems/regular-expression-matching/)（困难）

## 13. 刷题路线建议

- LeetCode：数组/哈希 → 双指针 → 链表 → 栈队列 → 二叉树 → 回溯 → 贪心 → DP → 图
- ACM：Codeforces Div.2 A-C 打基础 → 数据结构 + 图论 → DP 专题 → 打 VP 模拟赛

本笔记各专题的建议顺序见下一节。

## 14. 总学习路线（由易到难）

先把第 1 节的模板写成默认习惯，再按下面的顺序过专题。每一阶段先做该节的简单题，再做中等题；困难题用来确认这个模型能独立写出来。第 13 节里的链表、二叉树、贪心穿插在对应位置，不单独成节。

1. **STL 常用**（第 2 节）：哈希、排序、堆。对应「数组 / 哈希」。
2. **双指针 / 滑动窗口**（第 4 节）：对撞指针和窗口，只依赖数组遍历。
3. **前缀和 / 差分**（第 5 节）：区间查询和区间修改拆开，后面 DP、树状数组都会用到。
4. **二分**（第 3 节）：先做有序数组上的查找，再做二分答案。
5. **单调栈 / 单调队列**（第 6 节）：对应路线里的栈和队列，解决「下一个更大」和滑动窗口最值。链表放在这一步之前补完（双指针已经够用）。
6. **搜索**（第 7 节）：二叉树 DFS、网格 BFS，然后回溯（排列、组合、子集）。贪心放在回溯之后、DP 之前，多和排序、区间选择一起出现。
7. **动态规划**（第 8 节）：线性 DP 和背包先于区间 DP、树形 DP、状压 DP、数位 DP。
8. **字符串**（第 12 节）：公共前缀和子串匹配，再进入 KMP、字符串哈希、Manacher。
9. **数学**（第 11 节）：gcd、筛法、快速幂、逆元、组合数。竞赛里经常和取模 DP 绑在一起。
10. **图论**（第 9 节）：并查集和拓扑排序，再到 Dijkstra、最小生成树，最后是 Tarjan、LCA。
11. **数据结构（ACM 进阶）**（第 10 节）：Trie、树状数组、线段树、ST 表。
12. **整场训练**：回到第 1 节的模板，按第 13 节用 Codeforces Div.2 A–C、AtCoder、洛谷把上面的专题串起来。
