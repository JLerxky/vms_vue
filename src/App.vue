<template>
  <div id="app">
    <el-container style="height: 100%;">
      <el-header>
        <NavMenu></NavMenu>
      </el-header>
      <el-main style="height: 100%; margin-bottom: 40px;">
        <LiveAll></LiveAll>
      </el-main>
      <el-footer height="40px">@JLer</el-footer>
    </el-container>
  </div>
</template>

<script>
  import NavMenu from './components/NavMenu.vue'
  import LiveAll from './components/LiveAll.vue'
  export default {
    components: { NavMenu, LiveAll }
  }
</script>

<style>
  html{
    height: 100%;
  }
  #app{
    height: 100%;
  }
  body{
    margin: 0;
    background-color: #E9EEF3;
    min-width: 700px;
    height: 100%;
  }
  .el-card {
    height: 100%;
    overflow: auto;
  }
  a {
    text-decoration: none;
  }
  .el-header, .el-footer {
    background-color: #ffffff;
    color: #333;
    text-align: center;
    line-height: 40px;
  }

  .el-aside {
    background-color: #D3DCE6;
    color: #333;
    text-align: center;
    line-height: 200px;
  }

  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    /*line-height: 160px;*/
  }

  body > .el-container {
    margin-bottom: 40px;
  }

  footer.el-footer {
    height: 40px;
    position: absolute;
    bottom: 0;
    width: 100%;
  }

  .el-card__header {
    padding: 8px 10px;
  }

  .el-card__body {
    padding: 20px 0;
  }

  .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
    line-height: 260px;
  }

  .el-container:nth-child(7) .el-aside {
    line-height: 320px;
  }
</style>
