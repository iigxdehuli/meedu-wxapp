<template>
  <div class="video-list-item" @click="goVideo(item)">
    <div class="video-icon">
      <img class="video-icon__img" src="../assets/img/triangle-icon.png" alt mode="widthFix">
    </div>
    <div class="video-title">
      <span class="video-title-text">{{(index + 1) + ' . ' + item.title}}</span>
      <span class="video-title-icon">
        <img class="video-icon__img" src="../assets/img/turn-right-d.png" alt mode="widthFix">
      </span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    index: Number,
    item: Object
  },
  data() {
    return {};
  },
  methods: {
    goVideo(video) {
      this.$emit("goVideo", video);
    }
  }
};
</script>

<style lang="less">
.video-list-item {
  display: flex;
  align-items: center;
  .video-icon {
    display: flex;
    flex: 0 0 auto;
    width: 32rpx;
    height: 32rpx;
    border: 1px solid #787878;
    align-items: center;
    justify-content: center;
    border-radius: 32rpx;
    margin-right: 10px;
    transform: rotate(-90deg);
    &__img {
      flex: 0 0 auto;
      width: 20rpx;
      height: auto;
      position: relative;
      top: 3rpx;
    }
  }
  .video-title {
    display: flex;
    flex: 1;
    font-size: 13px;
    line-height: 2.6;
    border-bottom: 1px solid @border-color;
    justify-content: space-between;
    position: relative;
    &-text{
      display: inline-block;
      width: 550rpx;
      flex: 0 0 auto;
      overflow: hidden;
      white-space: nowrap;
      text-overflow: ellipsis;
    }
    &-icon{
      flex: 0 0 auto;
    }
  }
}
</style>
