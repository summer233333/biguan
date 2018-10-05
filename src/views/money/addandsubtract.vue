<template>
  <div class="app">
    <div class="platform">
      <div class="platform_title">提币管理</div>
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
          prop="BBCwallet"
          label="BBC钱包资产">
        </el-table-column>
        <el-table-column
          fixed="right"
          label="操作"
          width="100px"
        >
          <template slot-scope="scope">
            <el-button @click="handleClick(scope.row)" type="text" size="small">加币</el-button>
            <el-button type="text" size="small">减币</el-button>
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
      name: "addandsubtract",
      data() {
        return {
          tableData: [{
            id: 'BTC',
            phone: '13668945618',
            BBCwallet: '1.03261535',
          },{
            id: 'BTC',
            phone: '13668945618',
            BBCwallet: '1.03261535',
          },{
            id: 'BTC',
            phone: '13668945618',
            BBCwallet: '1.03261535',
          },{
            id: 'BTC',
            phone: '13668945618',
            BBCwallet: '1.03261535',
          },{
            id: 'BTC',
            phone: '13668945618',
            BBCwallet: '1.03261535',
          },{
            id: 'BTC',
            phone: '13668945618',
            BBCwallet: '1.03261535',
          }
          ],
          currentPage3: 1,
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
