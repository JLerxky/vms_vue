<template>
  <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
    <el-menu-item index="1">监控列表</el-menu-item>
    <el-menu-item index="2">地图监控</el-menu-item>
    <el-menu-item index="3">录像回放</el-menu-item>
    <h4 id="project_name">{{projectName}}</h4>
    <el-button id="user" type="text" icon="el-icon-menu">
      {{userName}}
    </el-button>
  </el-menu>
</template>

<script>
  export default {
    data() {
      return {
        activeIndex: '1',
        activeIndex2: '1',
        projectName: '',
        userName: this.$route.query.u
      };
    },
    methods: {
      handleSelect(key, keyPath) {
        console.log(key, keyPath);
      }
    },
    mounted: function() {
      this.$axios.post('/api/live/projectName',{
        tid:this.$route.query.tid
      })
        .then(response => {this.projectName = response.data});
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
