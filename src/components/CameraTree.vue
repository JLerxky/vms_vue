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
      ref="tree2"
      :render-content="renderContent">
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
      },

      renderContent(h, { node, data, store } ) {
        if (node.isLeaf) return (
          <span class="el-tree-node__label">
            <span>
              <el-button size="small" type="text" on-click={ () => this.play() }>{node.label}</el-button>
            </span>
          </span>);
        else return (
          <span class="el-tree-node__label">
            <span>
              <span>{node.label}</span>
            </span>
          </span>);
      },

      play(){
        alert('ok');
      }
    },

    data() {
      return {
        filterText: '',
        data2: [],
        defaultProps: {
          children: 'children',
          label: 'label'
        }
      };
    },
    mounted: function() {
      this.$axios.post('/api/live/cameraTree',{
        tid:this.$route.query.tid
      })
        .then(response => {this.data2 = response.data});
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
    overflow: inherit;
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
