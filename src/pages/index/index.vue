<template>
  <div class="container">
    <div class="controller">
      <div class="controller-round">
        <div class="controller-round-leading">
          发起一个
        </div>
        <div class="controller-round-text">
          群自我介绍
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import card from '@/components/card'

export default {
  data () {
    return {
      userInfo: {}
    }
  },

  components: {
    card
  },

  methods: {
    bindViewTap () {
      const url = '../template/main'
      wx.navigateTo({ url })
    },
    getUserInfo () {
      // 调用登录接口
      wx.login({
        success: () => {
          wx.getUserInfo({
            success: (res) => {
              this.userInfo = res.userInfo
            }
          })
        }
      })
    }
  },

  created () {
    // 调用应用实例的方法获取全局数据
    // this.getUserInfo()
  }
}
</script>

<style lang="scss">
$primary-color:       #da4e57;

.controller {
  padding: 70rpx;
  text-align: center;

  &-round {
    position: relative;
    background: $primary-color;
    display: inline-block;
    height: 220rpx;
    width: 220rpx;
    border-radius: 100%;
    font-size: 32rpx;
    box-sizing: border-box;
    text-align: center;

    &:focus {
      color: blue;
    }

    &-leading {
      color: #fff;
      position: absolute;
      top: 28%;
      left: 20%;
      right: 20%;
      font-weight: 600;
      // transform: translate(0, -50%)
    }

    &-text {
      font-size: 22rpx;
      color: #f0f0f0;
      position: absolute;
      top: 56%;
      left: 15%;
      right: 15%;
    }
  }
}
</style>
