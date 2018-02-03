<template>
  <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
    <el-menu-item index="1">监控列表</el-menu-item>
    <el-menu-item index="2">地图监控</el-menu-item>
    <el-menu-item index="3">录像回放</el-menu-item>
    <h4 id="project_name">{{projectName}}</h4>
    <el-button id="user" type="text" icon="el-icon-menu">
      {{userName}}
    </el-button>
    <!--<el-submenu index="2">-->
      <!--<template slot="title">我的工作台</template>-->
      <!--<el-menu-item index="2-1">选项1</el-menu-item>-->
      <!--<el-menu-item index="2-2">选项2</el-menu-item>-->
      <!--<el-menu-item index="2-3">选项3</el-menu-item>-->
    <!--</el-submenu>-->
    <!--<el-menu-item index="3"><a href="#" target="_blank">订单管理</a></el-menu-item>-->
  </el-menu>
</template>

<script>
  export default {
    data() {
      return {
        activeIndex: '1',
        activeIndex2: '1',
        projectName: '浙江省水利监控',
        userName: '用户'
      };
    },
    methods: {
      handleSelect(key, keyPath) {
        console.log(key, keyPath);
      }
    }
  }
</script>

<style>
  #project_name {
    margin: 0;
    line-height: 60px;
    position: absolute;
    left: 46.333%;
  }

  #user {
    font-size: 18px;
    line-height: 60px;
    margin: 0;
    border: 0;
    float: right;
    padding: 0;
  }
</style>
