<template>
  <div class="list">
    <div class="list-left">
      <icon type="success_no_circle" />
    </div>
    <div class="list-right">
      {{ content }}
    </div>
  </div>
</template>

<script>
export default {
  props: {
    content: {
      type: string,
      required: true
    }
  }
}
</script>

<style lang="scss">
.list {
  padding: 5rpx 0;
  display: flex;
  flex-direction: row;

  &-left {
    margin-right: 15rpx;
    background: red;
    width: 80rpx;
  }

  &-right {
    width: 150rpx;
    background: blue;
  }
}
</style>
