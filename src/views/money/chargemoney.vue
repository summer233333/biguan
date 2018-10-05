<template>
  <div class="app">
    <div class="platform">
      <div class="platform_title">充币管理</div>
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
          label="编号"
          type="index"
          width="50">
        </el-table-column>
        <el-table-column
          prop="user"
          label="用户名"
          width="100px"
        >
        </el-table-column>
        <el-table-column
          prop="currency"
          label="币种名称"
          width="100px">
        </el-table-column>
        <el-table-column
          prop="address"
          label="充币地址"
          width="300">
        </el-table-column>
        <el-table-column
          prop="number"
          label="充值数量">
        </el-table-column>
        <el-table-column
          prop="cratedate"
          label="创建时间">
        </el-table-column>
        <el-table-column
          prop="todate"
          label="到账时间">
        </el-table-column>
        <el-table-column
          prop="state"
          label="状态">
        </el-table-column>
        <el-table-column
          label="操作"
          width="100px">
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
        input1:'',
        options2: [{
          value: '选项1',
          label: '黄金糕'
        }, {
          value: '选项2',
          label: '双皮奶',
        }, {
          value: '选项3',
          label: '蚵仔煎'
        }, {
          value: '选项4',
          label: '龙须面'
        }, {
          value: '选项5',
          label: '北京烤鸭'
        }],
        value2:'',
        input3:'',
        tableData: [{
          user: '哈哈哈',
          currency: 'BTC',
          number:'1.1345315',
          address:'13da1f123d1as3f1da3f1a12d3s',
          cratedate:'2018-02-15 12:00:00',
          todate:'2018-02-15 12:00:00',
          state:'充值成功'
        },{
          user: '哈哈哈',
          currency: 'BTC',
          number:'1.1345315',
          address:'13da1f123d1as3f1da3f1a12d3s',
          cratedate:'2018-02-15 12:00:00',
          todate:'2018-02-15 12:00:00',
          state:'充值成功'
        },{
          user: '哈哈哈',
          currency: 'BTC',
          number:'1.1345315',
          address:'13da1f123d1as3f1da3f1a12d3s',
          cratedate:'2018-02-15 12:00:00',
          todate:'2018-02-15 12:00:00',
          state:'充值成功'
        },{
          user: '哈哈哈',
          currency: 'BTC',
          number:'1.1345315',
          address:'13da1f123d1as3f1da3f1a12d3s',
          cratedate:'2018-02-15 12:00:00',
          todate:'2018-02-15 12:00:00',
          state:'充值成功'
        },{
          user: '哈哈哈',
          currency: 'BTC',
          number:'1.1345315',
          address:'13da1f123d1as3f1da3f1a12d3s',
          cratedate:'2018-02-15 12:00:00',
          todate:'2018-02-15 12:00:00',
          state:'充值成功'
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
