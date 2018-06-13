<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style lang="scss">
body,html,div,ul,li,img,input,h1,h2,h3,dl,dd,dt,p,a,label{
  margin:0;
  padding:0;
}
html,body{
  width:100%;
  height:100%;
}
body{
  font-size:12px;
  font-family: '微软雅黑';
  overflow:hidden;
  #app {
    display:inline-block;
    text-align:center;
    width:100%;
    height:100%;
  }
}
</style>
