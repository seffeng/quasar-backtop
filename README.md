# Vue Quasar Backtop

## 示例

```vue
<template>
  <q-backtop />
</template>

<script>
import { QBacktop } from 'q-backtop'
export default {
  components: {
    QBacktop
  }
}
</script>
```

## 参数

```VUE
<q-backtop color="warning" icon="keyboard_arrow_up" text="back to top" :right="20" :bottom="50" :z-index="9999" :round="true" />
```

| 参数    | 类型    | 默认               | 说明         |
| ------- | ------- | ------------------ | ------------ |
| color   | string  | primary            | 颜色         |
| icon    | string  | vertical_align_top | 图标         |
| text    | string  | 返回顶部           | 鼠标悬停提示 |
| right   | int     | 20                 | 距离右侧距离 |
| bottom  | int     | 20                 | 距离底部距离 |
| z-index | int     | 999                | 样式 z-index |
| round   | boolean | true               | 是否圆形     |

