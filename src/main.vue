<template>
  <div v-scroll="handleScroll" class="backtop-container">
    <q-btn
      v-if="visible"
      :round="round"
      :color="color"
      class="fixed-bottom-right animate-pop"
      :style="positionStyle"
      @click="handleBacktop"
    >
      <q-icon :name="icon" />
      <q-tooltip v-if="text">
        {{ text }}
      </q-tooltip>
    </q-btn>
  </div>
</template>

<script>
import { scroll } from 'quasar'
const { setScrollPosition } = scroll

export default {
  name: 'Backtop',
  props: {
    round: {
      type: Boolean,
      default: true
    },
    position: {
      type: Number,
      default: 200
    },
    duration: {
      type: Number,
      default: 1000
    },
    color: {
      type: String,
      default: 'primary'
    },
    icon: {
      type: String,
      default: 'vertical_align_top'
    },
    text: {
      type: String,
      default: '返回顶部'
    },
    right: {
      type: Number,
      default: 20
    },
    bottom: {
      type: Number,
      default: 20
    },
    zIndex: {
      type: Number,
      default: 999
    }
  },
  data() {
    return {
      visible: false
    }
  },
  computed: {
    positionStyle() {
      return {
        'margin': `0 ${this.right}px ${this.bottom}px 0`,
        'z-index': this.zIndex
      }
    }
  },
  methods: {
    handleScroll(position) {
      if (position > this.position) {
        this.visible = true
      } else {
        this.visible = false
      }
    },
    handleBacktop() {
      setScrollPosition(window, 0, this.duration)
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
