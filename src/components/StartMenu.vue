<template>
  <section id="startmenu" :hidden="hideMenu">
    <section id="sidemenu">
      <div id="github-button" class="sidebar-button"></div>
      <div id="power-button" class="sidebar-button"></div>
    </section>
    <section id="menu-list">
      <div class="list-item">
        Snake
      </div>
    </section>
  </section>
</template>

<script>
import { mixin as clickaway } from 'vue-clickaway';

export default {
  mixins: [ clickaway ],
  data: function () {
    return {

    }
  },
  props: {
    hideMenu: Boolean,
  },
  methods: {
    hideStartMenu: function() {
      console.log(this.hideMenu);
      if(this.hideMenu == false){
        this.$emit('hide-menu-update');
      }
    },
  },
}
</script>

<style scoped>
  #startmenu{
    position: absolute;
    bottom: 40px;
    left: 0px;
    width: 300px;
    height: 400px;
    z-index: 2;
    background-color: rgba(42,42,42, .65);  
    backdrop-filter: blur(5px);
  }
  #sidemenu{
    float: left;
    width: 50px;
    height: 400px;
  }
  #menu-list{
    float: left;
    width: 250px;
    height: 400px;
  }
  .sidebar-button{
    width: 50px;
    height: 50px;
  }
  #power-button{
    background: url("../assets/power.png") no-repeat center center;
    position:absolute;
    bottom: 0px;
  }
  #github-button{
    background: url("../assets/github.png") no-repeat center center;
    position:absolute;
    bottom: 50px;
  }
  #taskbar div:hover{
    background-color: rgba(64,64,64, .65);  
    backdrop-filter: blur(5px);
  }
</style>