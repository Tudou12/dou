<template>
  <div id="Adopt">
    <nav-menu></nav-menu>
    <router-view/>
      <Side @indexSelect="listByCategory" ref="side"></Side>
    <div id="why">
      <why class="area"></why>
    </div>
    <div id="step">
      <step class="area"></step>
    </div>
    <div id="cat">
      <stray-cat class="area" ref="strayCat"></stray-cat>
    </div>
    <!-- <div id="dog">
      <stray-dog class="area"></stray-dog>
    </div> -->
    </div>
</template>
<script>
  import NavMenu from '../common/NavMenu';
  import Side from '../adopt/Side';
  import StrayCat from "../adopt/StrayCat";
  // import StrayDog from "../adopt/StrayDog";
  import Why from "../adopt/Why";
  import Step from "../adopt/Step";
export default {
  name: 'Adopt',
  components: {NavMenu,Side,StrayCat,Why,Step},
  data() {
    return {
    };
  },
    methods: {
      listByCategory () {
        var _this = this
        var aid = this.$refs.side.aid
        var url = 'category/' + aid + '/strays'
        this.$axios.get(url).then(resp => {
          if (resp && resp.status === 200) {
            _this.$refs.strayCat.side= resp.data
          }
        })
      }
    }
};
</script>
<style>
  .strays-area {
    width: 990px;
    margin-left: auto;
    margin-right: auto;
  }
*{
  margin: 0px;
}
.Sans-serif {
  position: relative;
  left: 200px;
  font-size: 30px;
}
.area {
    width: 1000px;
    margin-left: auto;
    margin-right: auto;
  }
</style>
