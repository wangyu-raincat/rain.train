# rain.train · C++ 算法训练笔记

**从 STL 与二分，到动态规划和图论：按知识点组织的 C++ / LeetCode / ACM 学习路线。**

C++ algorithm study notes with code snippets, topic-based LeetCode practice links, and a progression toward competitive programming.

[开始阅读](notes/cpp-algorithm-notes.md) · [刷题路线](notes/cpp-algorithm-notes.md#13-刷题路线建议) · [反馈问题](https://github.com/wangyu-raincat/rain.train/issues)

## 这里有什么

- **按主题找知识**：竞赛模板、STL、二分、滑动窗口、前缀和、单调栈、搜索、动态规划、图论、数据结构、数学和字符串。
- **把知识接到练习**：每个主题附 LeetCode 题目链接，并标注由易到难的练习顺序。
- **保留常用片段**：C++ 模板与关键思路放在笔记中，便于边学边查。
- **先选路线再刷题**：笔记末尾提供刷题路线与分阶段学习建议。

当前内容是一篇持续整理的综合笔记，包含代码片段和练习索引；不是完整题解集，也不代表已完成所有列出的题目。

## 从哪里开始

| 你的目标 | 建议入口 |
| --- | --- |
| 刚开始用 C++ 刷题 | [竞赛模板头](notes/cpp-algorithm-notes.md#1-竞赛模板头) → [STL 常用](notes/cpp-algorithm-notes.md#2-stl-常用) |
| 练习基础算法思维 | [二分](notes/cpp-algorithm-notes.md#3-二分)，再顺着笔记学习双指针、前缀和与单调结构 |
| 复习搜索与状态设计 | [搜索](notes/cpp-algorithm-notes.md#7-搜索) → [动态规划](notes/cpp-algorithm-notes.md#8-动态规划) |
| 进入竞赛常见专题 | [图论](notes/cpp-algorithm-notes.md#9-图论)，再学习数据结构、数学与字符串 |
| 想要一条完整路线 | [总学习路线](notes/cpp-algorithm-notes.md#14-总学习路线由易到难) |

直接在 GitHub 上打开笔记即可阅读，不需要安装项目依赖。代码片段需按题目补全输入、边界处理与主函数后再编译验证。

## 推荐使用方式

1. 阅读一个主题的概念与模板，先说明它解决什么问题。
2. 从简单题开始独立实现，再检查复杂度与边界条件。
3. 记录错误原因与适用条件；复习时优先重做卡住的题。

部分模板使用 `<bits/stdc++.h>`，更适合 GCC / GNU C++ 环境；其他编译器可能需要替换为标准头文件。

## 仓库结构

```text
rain.train/
├── README.md
└── notes/
    └── cpp-algorithm-notes.md   # 综合笔记、模板与题目索引
```

## 纠错与交流

欢迎通过 [Issues](https://github.com/wangyu-raincat/rain.train/issues) 或 Pull Request 补充内容。报告问题时，请附上对应章节、代码或题目链接，并说明反例或更正理由。

相关学习笔记：[rain.study](https://github.com/wangyu-raincat/rain.study)（HTML / CSS 与按主题整理的基础知识）。
