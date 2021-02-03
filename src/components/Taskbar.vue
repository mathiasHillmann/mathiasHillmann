<template>
  <nav id="taskbar">
    <div id="menu-logo" title="Menu Iniciar" v-on:click="hideMenu = !hideMenu">
      <img src="../assets/logo.jpg" />
    </div>
    <div id="clock">
      <span id="hour">{{hour}}</span>
      <br/>
      <span id="date">{{date}}</span>
    </div>
    <StartMenu :hideMenu="hideMenu" @hide-menu-update="hideMenu = true"/>
  </nav>
</template>

<script>
import StartMenu from './StartMenu.vue'
export default {
  components:{
    StartMenu,
  },
  data: function() {
    return {
      hour: null,
      date: null,
      hideMenu : true,
    }
  },
  methods: {
    setHour: function () {
      let h = ("0" + new Date().getHours()).slice(-2);
      let m = ("0" + new Date().getMinutes()).slice(-2);
      this.hour = `${h}:${m}`;
    },
    setDate: function () {
      this.date = new Intl.DateTimeFormat(['pt-br', 'pt']).format(new Date());
    },
  },
  mounted() {
    this.setHour();
    this.setDate();
    this.interval = setInterval(() => this.setHour(), 1000);
  }
}
</script>

<style scoped>
  #taskbar{
    position: absolute;
    bottom: 0;
    width: 100%;
    height: 40px;
    z-index: 1;
    background-color: rgba(32,32,32, .65);  
    backdrop-filter: blur(5px);
  }
  #taskbar div:hover{
    background-color: rgba(64,64,64, .65);  
    backdrop-filter: blur(5px);
  }
  #menu-logo{
    float: left;
    height: 100%;
    width: 50px;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  #menu-logo img{
    height: 32px;
    width: 32px;
  }
  #clock {
    display: table-cell;
    vertical-align: middle;
    text-align: center;
    float: right;
    height: 100%;
    width: 6%;
    color: #E5E7E9;
    font-family: Arial, Helvetica, sans-serif;
    margin-right: 0.5em;
  }
</style>