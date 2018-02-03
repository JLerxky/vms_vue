<template>
  <el-card class="box-card">
    <div slot="header" class="clearfix">
      <span style="float: left;">{{title}}</span>
      <el-tooltip class="item" effect="dark" content="关闭全部" placement="top">
        <el-button
          style="float: right; padding: 3px 0; margin: 0;"
          type="text" icon="el-icon-close"></el-button>
      </el-tooltip>
    </div>
    <div id="playOCX">
    </div>
  </el-card>
</template>

<script>
  export default {
    data() {
      return {
        title: '实时画面'
      };
    }
  }
</script>

<style>
  .text {
    font-size: 14px;
  }

  div#playOCX {
    min-height: 500px;
    background-color: dimgrey;
    margin: -20px;
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
