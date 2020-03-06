# 写 React / Vue 项目时为什么要在列表组件中写 key，其作用是什么？

`vue` 和 `react` 都是采用 diff 算法来对比新旧虚拟节点，从而更新节点。在 `vue`  的 diff 函数交叉对比中，当新节点跟旧节点`头尾交叉对比`没有结果时，会根据新节点的 `key` 去对比旧节点数组中的 `key`，从而找到相应旧节点（这里对应的是一个 key => index 的 map 映射）。如果没有找到就认为是一个新增节点。而如果没有 key，那么就会采用遍历查找的方式去找到对应的旧节点。一种一个 map 映射，另一种是遍历查找。相比而言，map 映射的速度更快。