<template>
  <div class="block">
    <div class="block-title">
      {{title}}
    </div>
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true
    }
  }
}
</script>

<style lang="scss">
.block {
  &-title {
    padding: 10rpx 0;
    font-size: 32rpx;
    font-weight: 800;
    color: #000;
  }
}
</style>
