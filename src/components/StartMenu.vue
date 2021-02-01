<template>
  <div id="startmenu" :hidden="hideMenu">
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      
    }
  },
  props: {
    hideMenu: Boolean,
  }
}
</script>

<style scoped>
  #startmenu{
    position: absolute;
    bottom: 10%;
    width: 20%;
    height: 40%;
    z-index: 1;
    background-color: rgba(32,32,32, .65);  
    backdrop-filter: blur(5px);
  }
</style>