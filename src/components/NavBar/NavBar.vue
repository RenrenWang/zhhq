<template>

  <header class="nav-bar">
        <span  v-if="isBack" class="iconfont icon-fanhui2 back" @click="back()"></span>
        <h1 class="nav-bar-title">{{title}}</h1>
        <span  v-if="rightIcon&&rightIcon!=''" :class="['iconfont',rightIcon] " @click="rightAction()"></span>
  </header>
  

  
</template>

<script>
export default {
  name: 'NavBar',
  props:{
    title:{
      type:String,
    
    },
    isBack:{
      type:Boolean,
     default:true
    },
    rightIcon:{
       type:String,
        default:''
    }
  },
  data () {
    return {
      
    }
  },
  methods:{
    back(){
      this.$router.go(-1);
    },
    rightAction(){
 
      this.$emit('rightActionF');
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../../assets/style/base.scss";
// .fillBox {
  // position: relative;
  // height:$navHeight;
  .nav-bar{
    box-shadow: 0 1px 3px rgba(0,0,0,.12), 0 1px 2px rgba(0,0,0,.24);
    background:#288bf0;
    color:#fff;
    height:$navHeight;
    width: 96%;
    display:flex;
    justify-content:space-between;
    align-items:center;
    padding:0 rem(15px);
    position:fixed;
    z-index: 99;
    box-shadow: 0  0  2px #fff;
    z-index:9999;
    .iconfont{
      font-size:rem(50px);
    }
    .nav-bar-title{
      position:absolute;
      left:50%;
      top:50%;
      font-size:18px;
      transform: translate(-50%,-50%);
    }
  }
// }

</style>