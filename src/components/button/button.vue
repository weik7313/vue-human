<template>
  <button class="btn" :class="classes">
    <slot></slot>
  </button>
</template>

<script>
  export default {
    props: {
      type: {
        type: String,
        default: 'secondary'
      },
      block: {
        type: Boolean,
        default: false
      },
      loading: {
        type: Boolean,
        twoWay: true,
        default: false
      }
    },
    computed: {
      classes () {
        let classes = {}

        // success, error, secondary, etc.
        classes[`is-${this.type}`] = true

        // block
        classes['is-block'] = this.block

        // disabled
        classes['is-disabled'] = this.disabled || this.loading

        return classes
      }
    }
  }
</script>