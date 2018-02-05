<template>
  <el-card class="box-card" style="overflow: hidden;">
    <div slot="header" class="clearfix">
      控制面板
    </div>
    <div id="ptz">
      <div class="bg-purple">
        <el-button-group>
          <el-button type="info" plain icon="el-icon-zoom-out" @click="ptz(0)"></el-button>
          <el-button type="info" plain icon="el-icon-arrow-up" @click="ptz(0)"></el-button>
          <el-button type="info" plain icon="el-icon-zoom-in" @click="ptz(0)"></el-button>
        </el-button-group>
        <el-button-group>
          <el-button type="info" plain icon="el-icon-arrow-left" @click="ptz(0)"></el-button>
          <el-button type="info" plain icon="el-icon-view" @click="ptz(0)"></el-button>
          <el-button type="info" plain icon="el-icon-arrow-right" @click="ptz(0)"></el-button>
        </el-button-group>
        <el-button-group>
          <el-button type="info" plain icon="el-icon-remove-outline" @click="ptz(0)"></el-button>
          <el-button type="info" plain icon="el-icon-arrow-down" @click="ptz(0)"></el-button>
          <el-button type="info" plain icon="el-icon-circle-plus-outline" @click="ptz(0)"></el-button>
        </el-button-group>
      </div>
      <div class="bg-purple">
        <el-dropdown style="width: 100%;" @command="ptz">
          <el-button style="width: 100%;">
            窗口数量<i class="el-icon-arrow-down el-icon--right"></i>
          </el-button>
          <el-dropdown-menu slot="dropdown">
            <el-dropdown-item command="a">1x1</el-dropdown-item>
            <el-dropdown-item command="b">2x2</el-dropdown-item>
            <el-dropdown-item command="c">3x3</el-dropdown-item>
            <el-dropdown-item command="d">4x4</el-dropdown-item>
            <el-dropdown-item command="e">2x2=5</el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
        <el-button style="width: 100%;" @click="ptz(0)">关闭选中</el-button>
        <el-button style="width: 100%;" @click="ptz(0)">关闭全部</el-button>
      </div>
    </div>
  </el-card>
</template>

<script>
  export default {
    methods: {
      ptz(command) {
        alert('ok'+command);
      }
    }
  }
</script>

<style>
  .text {
    font-size: 14px;
  }

  .el-tree-node>.el-tree-node__children {
    overflow: unset;
  }

  #ptz {
    min-width: 170px;
    margin: 0 5px;
  }

  #ptz .el-button-group button {
    border: 0;
    border-radius: 0;
  }

  #ptz .bg-purple {
    height: 120px;
    /*width: 168px;*/
    margin-bottom: 20px;
    padding: 5px;
  }

  #ptz .el-button+.el-button {
    margin-left: 0;
  }

  .clearfix:before,
  .clearfix:after {
    display: table;
    content: "";
  }
  .clearfix:after {
    clear: both
  }
</style>
