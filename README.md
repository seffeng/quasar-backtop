# Vue Quasar Backtop

## 安装

```shell
npm install q-backtop
```

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
<q-backtop :reverse="true" position="top-right" :scroll-offset="1000" icon="vertical_align_bottom" text="直达底部" />
```

| 参数    | 类型    | 默认               | 说明             |
| ------- | ------- | ------------------ | ---------------------- |
| scroll-offset | int | 200 | 滚动偏移量，从该位置开始在页面上显示该组件 |
| reverse | boolean | false              | 反向（直达底部）          |
| right   | int     | 20                 | 距离边界水平距离         |
| bottom  | int     | 20                 | 距离边界垂直距离       |
| position| string  | bottom-right       | 组件位置：top-right，top，right，bottom，left，...... |
| round   | boolean | true               | 是否圆形                 |
| icon    | string  | vertical_align_top | 图标                    |
| color   | string  | primary            | 颜色                    |
| glossy  | boolean | false              | 光泽效果                 |
| text    | string  | 返回顶部            | 鼠标悬停提示              |

## 备注

* 当 reverse 为 true 时，为反向效果，页面将滚动到底部，此时可修改参数：position，scroll-offset，icon，text 实现更好显示效果。