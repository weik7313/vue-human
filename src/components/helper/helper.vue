<template>
  <div v-if="validate.$error">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: 'mn-helper',
    props: {
      validate: Object
    },
    computed: {
      cssPrefix () {
        return this.$human.cssPrefix
      }
    }
  }
</script>
