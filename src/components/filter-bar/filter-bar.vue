<template>
  <div :class="[ `${cssPrefix}filter-bar`, { 'is-shadow': shadow } ]">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: 'mn-filter-bar',
    props: {
      shadow: {
        type: Boolean,
        default: false
      }
    },
    computed: {
      cssPrefix () {
        return this.$human.cssPrefix
      }
    }
  }
</script>
