<template>
  <q-page-scroller
    :scroll-offset="scrollOffset"
    :duration="duration"
    :reverse="reverse"
    :offset="[right, bottom]"
    :expand="expand"
    :position="position"
  >
    <div v-if="expand" :class="styleClass">
      {{ text === '' ? '返回顶部' : text }}
    </div>
    <q-btn v-else :fab-mini="round" :icon="icon" :color="color" :glossy="glossy">
      <q-tooltip v-if="text">
        {{ text }}
      </q-tooltip>
    </q-btn>
  </q-page-scroller>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'QBacktop',
  props: {
    scrollOffset: {
      type: Number,
      default: 200
    },
    duration: {
      type: Number,
      default: 300
    },
    reverse: {
      type: Boolean,
      default: false
    },
    right: {
      type: Number,
      default: 20
    },
    bottom: {
      type: Number,
      default: 20
    },
    expand: {
      type: Boolean,
      default: false
    },
    position: {
      type: String,
      default: 'bottom-right',
      validator: function (value) {
        return ['top-right', 'top-left', 'bottom-right', 'bottom-left', 'top', 'right', 'bottom', 'left'].indexOf(value) !== -1
      }
    },
    round: {
      type: Boolean,
      default: true
    },
    icon: {
      type: String,
      default: 'vertical_align_top'
    },
    color: {
      type: String,
      default: 'primary'
    },
    glossy: {
      type: Boolean,
      default: false
    },
    text: {
      type: String,
      default: '返回顶部'
    }
  },
  computed: {
    styleClass () {
      return `col cursor-pointer q-pa-sm bg-${this.color} text-white text-center`
    }
  }
})
</script>
