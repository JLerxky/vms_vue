<template>
  <el-row :gutter="20" style="height: 100%; min-height: 600px;">
    <el-col :xs="8" :sm="6" :md="5" :lg="4" :xl="4"><div class="grid-content bg-purple"><CameraTree></CameraTree></div></el-col>
    <el-col :xs="8" :sm="12" :md="14" :lg="16" :xl="17"><div class="grid-content bg-purple"><LivePlay></LivePlay></div></el-col>
    <el-col :xs="8" :sm="6" :md="5" :lg="4" :xl="3"><div class="grid-content bg-purple"><PTZ></PTZ></div></el-col>
  </el-row>
</template>

<script>
  import CameraTree from './CameraTree.vue'
  import PTZ from './PTZ.vue'
  import LivePlay from './LivePlay.vue'
  export default {
    components: { CameraTree, PTZ, LivePlay }
  }
</script>

<style>
  .el-col {
    border-radius: 4px;
    height: 100%;
  }
  .bg-purple-dark {
    background: #99a9bf;
  }
  .bg-purple {
    background: #d3dce6;
  }
  .bg-purple-light {
    background: #e5e9f2;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 36px;
    height: 100%;
  }
  .row-bg {
    padding: 10px 0;
    background-color: #f9fafc;
  }
</style>
