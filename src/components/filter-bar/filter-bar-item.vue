<template>
  <div
    :class="[ `${cssPrefix}filter-bar-item`, { 'is-bordered': bordered, 'is-active': active } ]"
    @click="onClick">
    <slot></slot>
    <mn-icon
      name="ios-arrow-down"
      v-if="arrow"
      :class="[`${cssPrefix}filter-bar-arrow`, { 'is-collapsed': isCollapsed }]">
    </mn-icon>
  </div>
</template>

<script>
  import Icon from '../icon/icon'

  export default {
    components: {
      [Icon.name]: Icon
    },
    name: 'mn-filter-bar-item',
    props: {
      bordered: {
        type: Boolean,
        default: false
      },
      // Show arrow
      arrow: {
        type: Boolean,
        default: false
      },
      active: {
        type: Boolean,
        default: false
      }
    },
    data () {
      return {
        isCollapsed: false
      }
    },
    computed: {
      cssPrefix () {
        return this.$human.cssPrefix
      }
    },
    methods: {
      onClick () {
        this.$emit('filter-click')
        this.isCollapsed = !this.isCollapsed
      }
    },
    watch: {
      isCollapsed (newVal) {
        if (newVal) {
          this.$emit('filter-opened')
        } else {
          this.$emit('filter-closed')
        }
      }
    }
  }
</script>
