<script>
export default {
  created() {}
}
</script>

<style>
/*
  字体图标1.0.1   字体图标文件只能使用线上路径或者 base64
*/
@font-face {
  font-family: "iconfont";
  src: url("//at.alicdn.com/t/font_614011_dnejexuhhhtr19k9.eot?t=1522819240352"); /* IE9*/
  src: url("//at.alicdn.com/t/font_614011_dnejexuhhhtr19k9.eot?t=1522819240352#iefix")
      format("embedded-opentype"),
    /* IE6-IE8 */
      url("data:application/x-font-woff;charset=utf-8;base64,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")
      format("woff"),
    url("//at.alicdn.com/t/font_614011_dnejexuhhhtr19k9.ttf?t=1522819240352")
      format("truetype"),
    /* chrome, firefox, opera, Safari, Android, iOS 4.2+*/
      url("//at.alicdn.com/t/font_614011_dnejexuhhhtr19k9.svg?t=1522819240352#iconfont")
      format("svg"); /* iOS 4.1- */
}

.iconfont {
  font-family: "iconfont" !important;
  /* 1.0.2 全局修改默认字号为 32rpx */
  font-size: 32rpx;
  font-style: normal;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.icon-xuanze:before {
  content: "\e608";
}

.icon-dianpu:before {
  content: "\e609";
}

.icon-gouwuche:before {
  content: "\e60a";
}

.icon-dingdan:before {
  content: "\e60b";
}

.icon-jiantouxia:before {
  content: "\e60c";
}

.icon-jiantoushang:before {
  content: "\e60d";
}

.icon-jiantouyou:before {
  content: "\e60e";
}

.icon-shanchu:before {
  content: "\e60f";
}

.icon-kefu:before {
  content: "\e610";
}

.icon-jiantouzuo:before {
  content: "\e611";
}

.icon-shezhi:before {
  content: "\e612";
}

.icon-xiaoxi:before {
  content: "\e616";
}

.icon-tuikuan:before {
  content: "\e617";
}

.icon-xiao:before {
  content: "\e618";
}

.icon-eye:before {
  content: "\e619";
}

.icon-eye-close:before {
  content: "\e61a";
}

.icon-bianji:before {
  content: "\e61b";
}

.icon-daifukuan:before {
  content: "\e61c";
}

.icon-daishouhuo:before {
  content: "\e61d";
}

.icon-shoucang-fill:before {
  content: "\e613";
}

.icon-shoucang:before {
  content: "\e614";
}

.icon-sousuo:before {
  content: "\e61e";
}

.icon-xuanze-fill:before {
  content: "\e615";
}

</style>
