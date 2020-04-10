<template>
  <div id="Home">
    <nav-menu></nav-menu>
    <router-view/>
      <!-- <switch></switch> -->
      <Side></Side>
    <div id="body">
      <img src="../../assets/image/home4.png" style="width:1000px;hight:50px;margin:10px;" />
        <!-- <div id="header-div">
          <div style="height: 150px"></div>
          <carousel></carousel>
          <quick-nav style="float: right;margin-top: -450px;margin-right: 480px"></quick-nav>
        </div> -->
        <div class="News">
        <News id="News" class="area"></News>
        </div>
        <div class="Step">
        <Step id="Step" class="area"></Step>
        </div>
        <div class="losts">
        <losts id="losts" class="area"></losts>
        </div>

        <div class="cat">
        <cat id="cat" class="area"></cat>
        </div>
    <el-row>
    </el-row>
      </div>
    </div>
</template>
<script>
  import NavMenu from '../common/NavMenu';
  import Losts from '../home/Losts';
    import Step from '../home/Step';
  import Cat from '../home/Cat';
  import News from '../home/News';
export default {
  name: "Home",
  components: {NavMenu,Losts,Cat,News,Step},
  data() {
    return {
    };
  },
  methods: {
    // handleSelect(key, keyPath) {
    //   console.log(key, keyPath);
    // }
  }
};
</script>
<style>
*{
  margin: 0px;
}
.Sans-serif {
  position: relative;
  left: 200px;
  font-size: 30px;
}
#body {
  margin: auto;
  /* background-color: rgb(233, 229, 229); */
  /* background-color: darksalmon; */
}
.area {
    width: 1000px;
    margin-left: auto;
    margin-right: auto;
  }
</style>
