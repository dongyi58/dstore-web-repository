<template>
  
    <view class="tabbar" >
      <block v-for="(item,index) of tabData" :key="index">
          <navigator  open-type="switchTab" :url="item.pagePath" >
              <view  class="iconfont "
                :class="[item.iconClass,index == pageIdx ? 'tabActived' :'']"
              >
              </view>
          </navigator>
      </block>
  </view>
  
</template>

<script>
export default {
  props: ['pageIdx'],
  data(){
    return{
      tabData:[
            {
              iconClass:'icon-home1',
              pagePath:'/pages/index/main'
            },
            {
              iconClass:'icon-yuan',
              pagePath:'/pages/discover/main'
            },
            {
              iconClass:'icon-gouwuche2',
              pagePath:'/pages/cart/main'
            },
            {
              iconClass:'icon-user3',
              pagePath:'/pages/user/main'
            }
        ],
    }
  },
 mounted() {
    
 },
}
</script>

<style scoped>
/* component/tabBar/tabBar.wxss */


@font-face {font-family: "iconfont";
    src: url('//at.alicdn.com/t/font_878693_s3y6tr53s2.eot?t=1541061131737'); /* IE9*/
    src: url('//at.alicdn.com/t/font_878693_s3y6tr53s2.eot?t=1541061131737#iefix') format('embedded-opentype'), /* IE6-IE8 */
    url('data:application/x-font-woff;charset=utf-8;base64,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') format('woff'),
    url('//at.alicdn.com/t/font_878693_s3y6tr53s2.ttf?t=1541061131737') format('truetype'), /* chrome, firefox, opera, Safari, Android, iOS 4.2+*/
    url('//at.alicdn.com/t/font_878693_s3y6tr53s2.svg?t=1541061131737#iconfont') format('svg'); /* iOS 4.1- */
  }
  
  .iconfont {
    font-family:"iconfont" !important;
    font-size:16px;
    font-style:normal;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
  
  .icon-search:before { content: "\e65c"; }
  
  .icon-discover:before { content: "\e67e"; }
  
  .icon-cart:before { content: "\e6af"; }
  
  .icon-home:before { content: "\e6b8"; }
  
  .icon-people:before { content: "\e736"; }
  
  .icon-caidan05:before { content: "\e604"; }
  
  .icon-user3:before { content: "\e8b1"; }
  
  .icon-gouwuche2:before { content: "\e708"; }
  
  .icon-wode2:before { content: "\e61e"; }
  
  .icon-yuan:before { content: "\e629"; }
  
  .icon-home1:before { content: "\e644"; }
  
  .icon-menu:before { content: "\e8c6"; }
  
  

.tabbar{
  z-index:999999;
   position:fixed;
   left:0;
   bottom:0;
   width:100%;
   background:#191919;
   color:#515151;
   z-index:9999
}
.tabbar>navigator{
    width:25%;
    float:left;
    text-align:center;
    padding:16px 0;
    font-size:20px;
}
.tabActived{
  color:#fff !important;
}
</style>
