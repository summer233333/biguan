<template>
  <div class="app">
    <div class="platform">
      <div class="platform_title">充币管理</div>
      <el-table
        :data="tableData"
        stripe
        style="width: 100%">
        <el-table-column
          prop="id"
          label="会员ID"
        >
        </el-table-column>
        <el-table-column
          prop="phone"
          label="会员手机号"
        >
        </el-table-column>
        <el-table-column
          prop="currency"
          label="币种">
        </el-table-column>
        <el-table-column
          prop="number"
          label="充入数量">
        </el-table-column>
        <el-table-column
          prop="date"
          label="充入时间"
          date>
        </el-table-column>
        <el-table-column
          prop="state"
          label="状态">
        </el-table-column>
        <el-table-column
          label="操作">
          <template slot-scope="scope">
            <el-button @click="handleClick(scope.row)" type="text" size="small">详情</el-button>
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
    name: "chargemoney",
    data() {
      return {
        tableData: [{
          id: 'BTC',
          phone: '13668945618',
          currency: 'BTC',
          number:'1.03261535',
          date:'2018-02-15 12:00:00',
          state:'已成功'
        },{
          id: 'BTC',
          phone: '13668945618',
          currency: 'BTC',
          number:'1.03261535',
          date:'2018-02-15 12:00:00',
          state:'已成功'
        },{
          id: 'BTC',
          phone: '13668945618',
          currency: 'BTC',
          number:'1.03261535',
          date:'2018-02-15 12:00:00',
          state:'已成功'
        },{
          id: 'BTC',
          phone: '13668945618',
          currency: 'BTC',
          number:'1.03261535',
          date:'2018-02-15 12:00:00',
          state:'已成功'
        },{
          id: 'BTC',
          phone: '13668945618',
          currency: 'BTC',
          number:'1.03261535',
          date:'2018-02-15 12:00:00',
          state:'已成功'
        }
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
</style>
