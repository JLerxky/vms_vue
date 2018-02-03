<template>
  <el-card class="box-card">
    <div slot="header" class="clearfix">
      控制面板
    </div>
    <div id="ptz">
      <div class="bg-purple">
        <el-button-group>
          <el-button type="info" plain icon="el-icon-zoom-out"></el-button>
          <el-button type="info" plain icon="el-icon-arrow-up"></el-button>
          <el-button type="info" plain icon="el-icon-zoom-in"></el-button>
        </el-button-group>
        <el-button-group>
          <el-button type="info" plain icon="el-icon-arrow-left"></el-button>
          <el-button type="info" plain icon="el-icon-view"></el-button>
          <el-button type="info" plain icon="el-icon-arrow-right"></el-button>
        </el-button-group>
        <el-button-group>
          <el-button type="info" plain icon="el-icon-remove-outline"></el-button>
          <el-button type="info" plain icon="el-icon-arrow-down"></el-button>
          <el-button type="info" plain icon="el-icon-circle-plus-outline"></el-button>
        </el-button-group>
      </div>
      <div class="bg-purple">
        <el-tooltip class="item" effect="dark" content="窗口数量" placement="top">
          <el-select v-model="value">
            <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value">
            </el-option>
          </el-select>
        </el-tooltip>
        <el-button style="width: 100%;">关闭选中</el-button>
        <el-button style="width: 100%;">关闭全部</el-button>
      </div>
    </div>
  </el-card>
</template>

<script>
  export default {
    data() {
      return {
        options: [{
          value: '1',
          label: '1x1'
        }, {
          value: '2',
          label: '2x2'
        }, {
          value: '3',
          label: '3x3'
        }, {
          value: '4',
          label: '4x4'
        }, {
          value: '5',
          label: '2x2+5'
        }],
        value: '4'
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

  .el-tree {
    overflow: auto;
  }

  #ptz {
    text-align: -webkit-center;
    min-height: 442px;
  }

  #ptz .bg-purple {
    height: 120px;
    width: 168px;
    margin-bottom: 20px;
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
