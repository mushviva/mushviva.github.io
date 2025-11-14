---
title: 探索 Vue 3 的 Composition API
date: 2025-11-13T13:00:00.000+00:00
lang: zh
description: 一篇关于如何使用 Vue 3 Composition API 提升代码可维护性的文章。
---

Vue 3 的 Composition API 带来了更灵活、更强大的组件逻辑组织方式。

## 为什么选择 Composition API？

在大型应用中，Options API 可能会导致组件逻辑分散在不同的选项（data, methods, computed）中，难以阅读和维护。

Composition API 通过 `setup` 函数，让我们能够将相关的逻辑代码组织在一起。

```vue
<script setup>
import { computed, ref } from 'vue'

// 计数器逻辑
const count = ref(0)
function increment() {
  count.value++
}

// 计算属性
const doubleCount = computed(() => count.value * 2)
</script>

<template>
  <div>
    <button @click="increment">
      Count: {{ count }}
    </button>
    <p>Double: {{ doubleCount }}</p>
  </div>
</template>
```
