<template>
<div id="body">
     <nav-menu></nav-menu>
    <router-view/>
    <switch></switch>
      <SideMenu></SideMenu>
  <div id="Lunbo">
    <el-carousel class="lun_imgs" ref="carousel" @click.native="linkTo">
           <el-carousel-item class="lun_img" v-for="item in imgs" v-bind:key="item.url" >
             <img :src="item.url"/>
           </el-carousel-item>
         </el-carousel>
</div>
  <div class="introduce">
    <vol-introduce id="vol-introduce"></vol-introduce>
  </div>
  <div class="activity">
  <activity id="activity"></activity>
  </div>
  <div class="his-activity">
  <his-activity id="his-activity"></his-activity>
  </div>
    <div class="activity-list">
  <activity-list id="activity-list"></activity-list>
  </div>
      <div class="activity-manage">
  <activity-manage id="activity-manage"></activity-manage>
  </div>
</div>
</template>
<script>
import NavMenu from '../common/NavMenu';
import SideMenu from './SideMenu';
import VolIntroduce from './VolIntroduce';
import Activity from './Activity';
import HisActivity from './HisActivity';
import ActivityList from './ActivityList';
import ActivityManage from './ActivityManage'

export default {
  name: 'Voluntary',
  components: {NavMenu,SideMenu,VolIntroduce,Activity,HisActivity,ActivityList,ActivityManage},
  data () {
    return {
      imgs: [
        {url: require('../../assets/image/lunbo.jpg'), link: '/content1'},
        {url: require('../../assets/image/lunbo2.jpg'), link: '/content1'},
        {url: require('../../assets/image/lunbo3.jpg'), link: '/content1'},
        {url: require('../../assets/image/lunbo4.jpg'), link: '/content1'},
      ],
    }
  },
   methods: {
      linkTo () {
      let activeIndex = this.$refs.carousel.activeIndex
      this.$router.push(this.imgs[activeIndex].link)
    },
    }
}
</script>
<style scoped >
.el-carousel__item h3 {
    color: #e3fdfd;
    font-size: 14px;
    opacity: 0.75;
    line-height: 150px;
    margin: 0;
  }
  .el-carousel__item:nth-child(2n) {
    background-color: #e3fdfd;
  }

  .el-carousel__item:nth-child(2n+1) {
     background-color: #e3fdfd;
  }
  #Lunbo{
    background-color: aquamarine;
    width: 1000px;
    margin: auto;
  }
/* p{
  position: relative;
  left: 580px;
  margin: 0;
} */
img{
  width: 800px;
  height: 400px;
}

</style>
