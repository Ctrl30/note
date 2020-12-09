## React 源码
### 1. Fiber节点 （render阶段）
```
beginWork(current,workInProgress,renderLanes)
completeWork(current, workInProgress, renderLanes)

1. current:当前应用根节点进入时current有值，其值参考源码中的react-reconciler/ReactWorkTags.js,不是根节点进入时current为null(首屏渲染时，当前应用的current才有值，其他节点存在在workInProgress中)

2. workInProgress 根据深度优先原则，如果当前节点存在子节点，则继续执行beginWork，如果不存在子节点，则进入completeWork（react对只有一个文本节点的节点，不会生产fiber节点例如<code>hello</code> 会执行code的beginWork=>code 的completeWork，没有进入code的子节点在进行beginWork->completeWork）
3. 当当前节点没有兄弟节点的时候，会进入父节点的completeWork。
如此递归结束
```
### 2. Fiber节点 （commit阶段）

```

```