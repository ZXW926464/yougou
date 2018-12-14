<template>
   <!-- 顶部搜索栏 -->
    <div class="nav">
      <input type="text" placeholder="搜索">
    </div>
    
</template>

<script>
export default {
  
}
</script>

<style lang="scss">
$uRed: #ff2d4a;
//搜索框样式
.nav{
  padding: 20rpx 16rpx;
  background-color: $uRed;
  input{
    background-color: #fff;
    height: 60rpx;
    text-align: center;
    color: #bbbbbb;
    font-size: 24rpx;
    border-radius: 5rpx;
  }
}
</style>
