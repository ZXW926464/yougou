<template>
  <div class="index">
    <search></search>
    <!-- 轮播图 -->
    <swiper indicator-dots autoplay circular class="swiper">
            <swiper-item v-for="(item, index) in swiperList" :key="index">
                <image mode="aspectFill" :src="item.image_src"></image>
            </swiper-item>
    </swiper>

    <!-- 分类 -->
    <div class="category_box">
      <div class="item" v-for="(item, index) in categoryList" :key="index">
        <img :src="item.image_src" alt="">
        <text>{{item.name}}</text>
      </div>
    </div>

  <!-- 楼层 -->
    <div class="floor" v-for="(item, index) in floorList" :key="index">
      <div class="title">
        <h2>{{item.floor_title.name}}</h2>
        <img :src="item.floor_title.image_src" alt="">
      </div>
      <div class="bottom">
        <div class="item" v-for="(it, i) in item.product_list">
          <img :src="it.image_src" alt="">
        </div>
      </div>
    </div>

   <!-- 底线 -->
    <div class="bottom">
      <!-- :before :after的区别 内容的前面 内容的后面 只能让哪些标签使用  -->
      <i class="iconfont icon-xiao">我是有底线的</i>
    </div>
    <!-- 返回顶部 -->
    <div
      class="backtop"
      v-show="isShow"
      @click="backTop"
    >
      <i class="iconfont icon-jiantoushang"></i>
      顶部
    </div>
  </div>
</template>

<script>
//导入自己封装的
  import hxios from "../../utils/index.js"
  import search from "../../components/search.vue"

export default {
  data:function () { 
    return{
      //轮播图数据
      swiperList:[],
      //分类数据
      categoryList:[],
      //楼层数据
      floorList:[],
      isShow:false
    }
  },
  components:{
    search
  },
  // 小程序生命周期钩子
  onPageScroll(e) {
    // console.log(e);
    // console.log('滚了')
    if (e.scrollTop > 150) {
      this.isShow = true;
    } else {
      this.isShow = false;
    }
  },
  methods:{
    backTop(){
       wx.pageScrollTo({
        scrollTop: 0
        // duration: 300
      });
    }
  },
  created(){
    //获取数据
    let swiper =hxios.get('api/public/v1/home/swiperdata');
    let category =hxios.get('api/public/v1/home/catitems');
    let floor =hxios.get('api/public/v1/home/floordata');

    //一次性获取数据
    Promise.all([swiper,category,floor]).then(
      res=>{
        // console.log(res);
        this.swiperList=res[0].data.message
        this.categoryList=res[1].data.message
        this.floorList=res[2].data.message
      }
    )
  }
}
</script>
<style lang="scss">
$uRed: #ff2d4a;
// 轮播图
.swiper {
  image {
    width: 100%;
  }
}
// 分类
.category_box {
  display: flex;
  padding: 24rpx 0 29rpx;
  .item {
    flex: 1;
    image {
      display: block;
      width: 95rpx;
      height: 95rpx;
      margin: 0 auto;
    }
    text {
      font-size: 24rpx;
      display: block;
      text-align: center;
      margin-top: 15rpx;
    }
  }
}

// 楼层数据
.floor{
  .title {
    position: relative;
    h2 {
      position: absolute;
      color: #ff7b94;
      font-size: 35rpx;
      font-weight: 700;
      top: 50%;
      left: 16rpx;
      transform: translateY(-50%);
    }
    img {
      width: 100%;
      height: 90rpx;
    }
  }
  .bottom {
    padding: 20rpx 16rpx;
    overflow: hidden;
    .item {
      width: 33.333%;
      float: left;
      padding-right: 10rpx;
      box-sizing: border-box;
      img {
        display: block;
        height: 480rpx;
        width: 100%;
      }
    }
    .item:not(:first-child) {
      padding-bottom: 10rpx;
      img {
        height: 235rpx;
      }
    }
  }
}
//  底部
.bottom {
  text-align: center;
  display: block;
  color: #999999;
}
// 返回顶部
.backtop {
  text-align: center;
  position: fixed;
  width: 90rpx;
  height: 90rpx;
  right: 10rpx;
  bottom: 10rpx;
  border-radius: 50%;
  background-color: $uRed;
  color: white;
  font-size: 24rpx;
  .iconfont {
  }
} 
</style>
