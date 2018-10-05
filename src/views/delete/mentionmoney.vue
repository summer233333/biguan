<template>
  <div class="app">
    <div class="platform">
      <div class="platform_title">提币管理</div>
      <div class="search">
        <el-input
          placeholder="请输入用户名"
          v-model="input1"
          class="search_user"
          prefix-icon="el-icon-search"
          clearable
        >
        </el-input>
        <el-select v-model="value2" placeholder="请选择状态"
                   class="search_user">
          <el-option
            v-for="item in options2"
            :key="item.value"
            :label="item.label"
            :value="item.value"
            :disabled="item.disabled"
          >
          </el-option>
        </el-select>
        <el-select v-model="value2" placeholder="请选择币种名称"
                   class="search_user">
          <el-option
            v-for="item in options2"
            :key="item.value"
            :label="item.label"
            :value="item.value"
            :disabled="item.disabled"
          >
          </el-option>
        </el-select>
        <el-button type="primary" round>搜索</el-button>
      </div>
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
          label="提币数量">
        </el-table-column>
        <el-table-column
          prop="poundage"
          label="手续费"
          >
        </el-table-column>
        <el-table-column
          prop="date"
          label="充入时间"
          >
        </el-table-column>
        <el-table-column
          prop="state"
          label="状态">
        </el-table-column>
        <el-table-column
          fixed="right"
          label="操作"
          >
          <template slot-scope="scope">
            <el-button @click="handleClick(scope.row)" type="text" size="small">同意</el-button>
            <el-button type="text" size="small">驳回</el-button>
            <el-button type="text" size="small">冻结</el-button>
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
    name: "mentionmoney",
    data() {
      return {
        tableData: [{
          id: 'BTC',
          phone: '13668945618',
          currency: 'BTC',
          number:'1.03261535',
          poundage:'1.03261535',
          date:'2018-02-15 12:00:00',
          state:'已成功'
        },{
          id: 'BTC',
          phone: '13668945618',
          currency: 'BTC',
          number:'1.03261535',
          poundage:'1.03261535',
          date:'2018-02-15 12:00:00',
          state:'已成功'
        },{
          id: 'BTC',
          phone: '13668945618',
          currency: 'BTC',
          number:'1.03261535',
          poundage:'1.03261535',
          date:'2018-02-15 12:00:00',
          state:'已成功'
        },{
          id: 'BTC',
          phone: '13668945618',
          currency: 'BTC',
          number:'1.03261535',
          poundage:'1.03261535',
          date:'2018-02-15 12:00:00',
          state:'已成功'
        },{
          id: 'BTC',
          phone: '13668945618',
          currency: 'BTC',
          number:'1.03261535',
          poundage:'1.03261535',
          date:'2018-02-15 12:00:00',
          state:'已成功'
        },{
          id: 'BTC',
          phone: '13668945618',
          currency: 'BTC',
          number:'1.03261535',
          poundage:'1.03261535',
          date:'2018-02-15 12:00:00',
          state:'已成功'
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
  .search {
    display: flex;
    background-color: white;
    padding: 10px 0;
    border-top: 1px solid #E3E3E3;
    border-bottom: 1px solid #E3E3E3;
  }
  .search_user {
    width: 220px;
    margin-left: 10px;
    margin-right: 20px;
  }
</style>
