<template lang="">
  <div class="root">
    <!-- Session One -->
    <div class="session-one">
      <div class="header">
        <el-header>Header</el-header>
      </div>
      <div class="carousel-one">
        <el-carousel :interval="5000" arrow="always">
          <el-carousel-item v-for="(item,index) in imageBanners" :key="index">
              <img :src="require(`../assets/Banners/${item.url}`)" />
          </el-carousel-item>
        </el-carousel>
      
      </div>
    </div>
    <!-- Session Two -->
    <div class="session-two">
      <el-carousel :interval="4000" type="card" height="200px">
        <el-carousel-item v-for="item in 6" :key="item">
          <h3 class="medium">{{ item }}</h3>
        </el-carousel-item>
      </el-carousel>
      
    </div>
    


  </div>
</template>
<script>
// import aaa from '../assets/Banners/coffee1.jpg'
export default {
  name:"Home",
  data() {
    return{
      imageBanners: [
        {url: 'coffee1.jpg'},
        {url: 'coffee2.jpg'},
        {url: 'coffee3.jpg'},
        {url: 'coffee4.jpg'},
      ]
    }
  },
  methods:{
    requireImg(img){
      return require(`${{img}}`)
    }
  }
}
</script>
<style scoped lang="scss">
  .el-carousel__item h3 {
    /* color: #475669; */
    font-size: 14px;
    opacity: 0.75;
    line-height: 200px;
    margin: 0;
  }
 
  .el-carousel__item:nth-child(2n) {
    background-color: #99a9bf;
  }

  .el-carousel__item:nth-child(2n+1) {
    background-color: #d3dce6;
  }
  .session-one  .el-header{
    background-color: blue;
  }
  .session-one{
    margin-bottom: 50px;
  }
  .el-carousel{
    text-align: center;
  }
  .session3{
    background-color: black;
  }
</style>