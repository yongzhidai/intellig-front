<template>
  <div class="table-content">
    <el-table
        :data="tableData"
        stripe
        style="width: 600px">
        <el-table-column
        prop="id"
        label="ID"
        width="80">
        </el-table-column>
        <el-table-column
        prop="name"
        label="名称"
        width="180">
        </el-table-column>
        <el-table-column
        prop="code"
        label="编码">
        </el-table-column>
        <el-table-column
        prop="createTime"
        label="创建时间">
        </el-table-column>
    </el-table>
  </div>
</template>
<style lang="css" scoped>
    .table-content{
        margin :auto;
        width :600px;
    }
</style>
<script>
  export default {
    data() {
      var data = {};
      data.tableData = this.getData();
      return data;
    },
    methods:{
        getData(){
            this.$http.get('/test.do').then(function(resp){
                console.log(resp.data);
                this.tableData = resp.data;
            },function(){
                this.$message.error('获取数据失败！');
            });
        }
    }
  }
</script>