<template>
  <div class="app">
    <div class="platform">
      <div class="platform_title">用户资金管理</div>
      <div class="search">
        <el-input
          placeholder="输入用户名/邮箱/手机号"
          v-model="input1"
          class="search_user"
          prefix-icon="el-icon-search"
          clearable
        >
        </el-input>
        <el-input
          placeholder="输入钱包地址"
          v-model="input2"
          class="search_user"
          prefix-icon="el-icon-search"
          clearable
        >
        </el-input>
        <el-input
          placeholder="输入币种搜索"
          v-model="input3"
          class="search_user"
          prefix-icon="el-icon-search"
          clearable
        >
        </el-input>
        <el-button type="primary" round>搜索</el-button>
      </div>
      <el-table
        :data="tableData"
        stripe
        style="width: 100%">
        <el-table-column
          label="编号"
          type="index"
          width="50">
        </el-table-column>
        <el-table-column
          prop="user"
          label="用户名"
          width="150px"
        >
        </el-table-column>
        <el-table-column
          prop="email"
          label="邮箱"
          width="200"
          >
        </el-table-column>
        <el-table-column
          prop="phone"
          label="充币地址">
        </el-table-column>
        <el-table-column
          prop="truename"
          label="真实姓名">
        </el-table-column>
        <el-table-column
          prop="coin_name"
          label="币种名称">
        </el-table-column>
        <el-table-column
          prop="money_address"
          label="钱包地址"
          width="300">
        </el-table-column>
        <el-table-column
          prop="available_coin"
          label="可用币数">
        </el-table-column>
        <el-table-column
          prop="freeze_coin"
          label="冻结币数">
        </el-table-column>
        <el-table-column
          prop="sum_coin"
          label="总币个数">
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
    name: "Money_management",
    data() {
      return {
        input1:'',
        input2:'',
        input3:'',
        tableData: [{
          user: '哈哈哈',
          email: '545464564@qq.com',
          phone:'13990734392',
          truename:'李四',
          coin_name:'BTC',
          money_address:'1fd3sa1f23da1fd1a3fafd12a31f23a',
          available_coin:'0',
          freeze_coin:'0',
          sum_coin:'0',
        },{
          user: '哈哈哈',
          email: '545464564@qq.com',
          phone:'13990734392',
          truename:'李四',
          coin_name:'BTC',
          money_address:'1fd3sa1f23da1fd1a3fafd12a31f23a',
          available_coin:'0',
          freeze_coin:'0',
          sum_coin:'0',
        },{
          user: '哈哈哈',
          email: '545464564@qq.com',
          phone:'13990734392',
          truename:'李四',
          coin_name:'BTC',
          money_address:'1fd3sa1f23da1fd1a3fafd12a31f23a',
          available_coin:'0',
          freeze_coin:'0',
          sum_coin:'0',
        },{
          user: '哈哈哈',
          email: '545464564@qq.com',
          phone:'13990734392',
          truename:'李四',
          coin_name:'BTC',
          money_address:'1fd3sa1f23da1fd1a3fafd12a31f23a',
          available_coin:'0',
          freeze_coin:'0',
          sum_coin:'0',
        },{
          user: '哈哈哈',
          email: '545464564@qq.com',
          phone:'13990734392',
          truename:'李四',
          coin_name:'BTC',
          money_address:'1fd3sa1f23da1fd1a3fafd12a31f23a',
          available_coin:'0',
          freeze_coin:'0',
          sum_coin:'0',
        },{
          user: '哈哈哈',
          email: '545464564@qq.com',
          phone:'13990734392',
          truename:'李四',
          coin_name:'BTC',
          money_address:'1fd3sa1f23da1fd1a3fafd12a31f23a',
          available_coin:'0',
          freeze_coin:'0',
          sum_coin:'0',
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
  .search {
    display: flex;
    background-color: white;
    padding: 10px 0;
    border-top: 1px solid #E3E3E3;
    border-bottom: 1px solid #E3E3E3;
  }
  .search_user {
    width: 250px;
    margin-left: 10px;
    margin-right: 20px;
  }
</style>
