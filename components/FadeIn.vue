<template>
  <span>
    <transition name="slide-fade">
      <slot v-if="visible"></slot>
    </transition>
  </span>
</template>

<script>
export default {
  data() {
    return {
      visible: false,
    }
  },
  methods: {
    handleScroll() {
      if (!this.visible) {
        let top = this.$el.getBoundingClientRect().top
        this.visible = top < window.innerHeight
      }
    },
  },
  created() {
    window.addEventListener('scroll', this.handleScroll)
  },
  destroyed() {
    window.removeEventListener('scroll', this.handleScroll)
  },
}
</script>

<style lang="scss">
.slide-fade-enter-active {
  transition: all 2s ease;
}

.slide-fade-enter {
  transform: translateX(300px);
  opacity: 0;
}
</style>
