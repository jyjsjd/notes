---
title: String 操作
tags: [Shell]
created: '2019-07-02T08:04:58.856Z'
modified: '2019-07-02T08:12:56.733Z'
---

# String 操作

- `${#string}`：返回字符串长度

- `${string:position}`：返回子字符串

- `${string:position:length}`：返回指定长度的子字符串

- `${string#substring}`：从前删除最短子串

- `${string##substring}`：从前删除最长子串

- `${string%substring}`：从后删除最短子串

- `${string%%substring}`：从后删除最长子串

- `${string/substring/replacement}`：替换首个子串

- `${string//substring/replacement}`：替换所有子串

- `${string/#substring/replacement}`：从前替换

- `${string/%substring/replacement}`：从后替换
