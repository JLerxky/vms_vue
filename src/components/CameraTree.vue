<template>
  <el-card class="box-card">
    <div slot="header" class="clearfix">
      <el-input
        placeholder="输入关键字进行过滤"
        v-model="filterText">
      </el-input>
    </div>
    <el-tree
      id="camera_tree"
      class="filter-tree"
      :data="data2"
      :props="defaultProps"
      :filter-node-method="filterNode"
      ref="tree2">
    </el-tree>
  </el-card>
</template>

<script>
  export default {
    watch: {
      filterText(val) {
        this.$refs.tree2.filter(val);
      }
    },

    methods: {
      filterNode(value, data) {
        if (!value) return true;
        return data.label.indexOf(value) !== -1;
      }
    },

    data() {
      return {
        filterText: '',
        data2: [{
          id: 1,
          label: '宁波',
          children: [{
            id: 4,
            label: '二级 1-1-1-1-1-1-1-1-1-1-1-1-1-11-1-1-1-1-1-1-1-1-1-1-1-1-1',
            children: [{
              id: 9,
              label: '三级 1-1-1'
            }, {
              id: 10,
              label: '三级 1-1-2'
            }]
          }]
        }, {
          id: 2,
          label: '金华',
          children: [{
            id: 5,
            label: '二级 2-1'
          }, {
            id: 6,
            label: '二级 2-2'
          }]
        }, {
          id: 3,
          label: '杭州',
          children: [{
            id: 7,
            label: '二级 3-1'
          }, {
            id: 8,
            label: '二级 3-2'
          }]
        }],
        defaultProps: {
          children: 'children',
          label: 'label'
        }
      };
    }
  };
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

  div#camera_tree {
    min-height: 443px;
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
