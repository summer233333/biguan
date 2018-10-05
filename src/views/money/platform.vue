<template>
  <div class="app">
    <div class="platform">
      <div class="platform_title">平台资金管理</div>
      <el-table
        :data="tableData"
        stripe
        style="width: 100%">
        <el-table-column
          prop="currency"
          label="币种"
         >
        </el-table-column>
        <el-table-column
          prop="address"
          label="地址"
          >
        </el-table-column>
        <el-table-column
          prop="assets"
          label="总资产">
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
    name: "flatform",
    data() {
      return {
        tableData: [{
          currency: 'BTC',
          address: 'EWQEWQEWQEQEWQ',
          assets: '123.45648',
          operation:'详情'
        },{
          currency: 'BTC',
          address: 'EWQEWQEWQEQEWQ',
          assets: '123.45648',
          operation:'详情'
        },{
          currency: 'BTC',
          address: 'EWQEWQEWQEQEWQ',
          assets: '123.45648',
          operation:'详情'
        },{
          currency: 'BTC',
          address: 'EWQEWQEWQEQEWQ',
          assets: '123.45648',
          operation:'详情'
        },{
          currency: 'BTC',
          address: 'EWQEWQEWQEQEWQ',
          assets: '123.45648',
          operation:'详情'
        },{
          currency: 'BTC',
          address: 'EWQEWQEWQEQEWQ',
          assets: '123.45648',
          operation:'详情'
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
</style>
