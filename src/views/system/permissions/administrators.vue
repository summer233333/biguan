<template>
  <div class="app">
    <div class="platform">
      <div class="platform_title">管理员管理</div>
      <div class="management">
        <el-button type="success" round class="add">添加管理员</el-button>
        <el-button type="primary" round>批量删除</el-button>
      </div>
      <el-table
        :data="tableData"
        stripe
        style="width: 100%">
        <el-table-column
          type="selection"
          width="40">
        </el-table-column>
        <el-table-column
          label="编号"
          type="index"
          width="50">
        </el-table-column>
        <el-table-column
          prop="administrator_name"
          label="管理员名称"
        >
        </el-table-column>
        <el-table-column
          prop="name"
          label="姓名"
        >
        </el-table-column>
        <el-table-column
          prop="login_number"
          label="登录次数"
        >
        </el-table-column>
        <el-table-column
          prop="last_login_time"
          label="最后登录时间">
        </el-table-column>
        <el-table-column
          prop="state"
          label="状态">
        </el-table-column>
        <el-table-column
          label="操作">
          <template slot-scope="scope">
            <el-button @click="handleClick(scope.row)" type="text" size="small">编辑</el-button>
            <el-button @click="handleClick(scope.row)" type="text" size="small">禁用</el-button>
            <el-button @click="handleClick(scope.row)" type="text" size="small">删除</el-button>
          </template>
        </el-table-column>
      </el-table>

      <!--分页-->
      <div class="block">
        <el-pagination
          background
          align="right"
          @size-change="handleSizeChange"
          @current-change="handleCurrentChange"
          :current-page.sync="currentPage3"
          :page-size="5"
          layout="prev, pager, next, jumper"
          :total="25">
        </el-pagination>
      </div>
    </div>
  </div>

</template>

<script>
  export default {
    name: "administrator",
    data() {
      return {
        tableData: [{
          administrator_name: '超级管理员',
          name: '张三',
          login_number:'12',
          last_login_time:'2018-09-28 10:00:00',
          state:'正常',
        },{
          administrator_name: '超级管理员',
          name: '张三',
          login_number:'12',
          last_login_time:'2018-09-28 10:00:00',
          state:'正常',
        },{
          administrator_name: '超级管理员',
          name: '张三',
          login_number:'12',
          last_login_time:'2018-09-28 10:00:00',
          state:'正常',
        },{
          administrator_name: '超级管理员',
          name: '张三',
          login_number:'12',
          last_login_time:'2018-09-28 10:00:00',
          state:'正常',
        },{
          administrator_name: '超级管理员',
          name: '张三',
          login_number:'12',
          last_login_time:'2018-09-28 10:00:00',
          state:'正常',
        },
        ],
        currentPage3: 5,
      }
    },
    methods: {
      handleSizeChange(val) {
        console.log(`每页 ${val} 条`);
      },
      handleCurrentChange(val) {
        console.log(`当前页: ${val}`);
      }
    },
  }
</script>

<style scoped>
  .app {
    background-color: rgb(242,243,247);
  }
  .platform {
    margin-left: 20px;
    margin-right: 20px;
  }
  .platform_title {
    padding-top: 20px;
    margin-bottom: 20px;
    font-weight: 600;
  }
  .management {
    display: flex;
    background-color: white;
    padding: 10px 0;
    border-top: 1px solid #E3E3E3;
    border-bottom: 1px solid #E3E3E3;
  }
  .add {
    margin-left: 10px;
    margin-right: 20px;
  }
</style>
