<template>
  <div :class="[ `${cssPrefix}tab-content` ]" v-if="this.$parent.flag === this._uid && this.show">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: 'mn-tab-bar-pane',
    props: {
      title: {
        type: String
      },
      icon: {
        type: String
      },
      link: {
        type: String
      },
      show: {
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
