<template>
  <q-page-scroller
    :scroll-offset="scrollOffset"
    :duration="duration"
    :reverse="reverse"
    :offset="[right, bottom]"
    :expand="expand"
    :position="position"
  >
    <div v-if="expand" class="col cursor-pointer q-pa-sm bg-accent text-white text-center">
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
export default {
  name: 'Backtop',
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
      default: 'bottom-right'
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
  }
}
</script>

<style lang="scss" scoped>

</style>
