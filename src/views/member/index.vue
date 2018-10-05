<template>
  <div class="member">
    <!-- <component :is="currentRole"/> -->
    <div class="search">
        <el-input placeholder="搜索会员" prefix-icon="el-icon-search" v-model="input21"></el-input>
        <el-select v-model="value" placeholder="实名状态">
            <el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value">
            </el-option>
        </el-select>
        <el-button type="primary" @click="dialogFormVisible = true">搜索</el-button>
    </div>
    <el-table
    class="tablebox"
    stripe
    fit
    ref="multipleTable"
    :data="tableData3"
    tooltip-effect="dark"
    style="width: 100%"
    @selection-change="handleSelectionChange">
    <el-table-column type="selection" width="55">
    </el-table-column>
    <el-table-column label="会员ID" min-width="150">
      <template slot-scope="scope">{{ scope.row.id }}</template>
    </el-table-column>
    <el-table-column label="登录手机" min-width="150">
        <template slot-scope="scope">{{ scope.row.phone }}</template>
    </el-table-column>
    <el-table-column label="注册时间" min-width="150">
      <template slot-scope="scope">{{ scope.row.date }}</template>
    </el-table-column>
    <el-table-column label="实名状态" min-width="150">
        <template slot-scope="scope">
             <el-button type="success" size="mini" v-if="scope.row.autonymState =='A'">未实名</el-button>
             <el-button type="info" size="mini" v-else-if="scope.row.autonymState == 'B'">已提交</el-button>
             <el-button type="warning" size="mini" v-else-if="scope.row.autonymState == 'C'">已实名</el-button>
        </template>
    </el-table-column>
    <el-table-column label="状态" min-width="150">
        <template slot-scope="scope">
            <span v-if="scope.row.state== '1'">正常</span>
            <span v-else style="color:red;">禁用</span>
        </template>
    </el-table-column>
    <el-table-column label="操作" min-width="150">
        <template slot-scope="scope">
        <el-button type="text" @click="handleClick(scope.row)">详情</el-button>
        <el-button type="text" @click="handleClick(scope.row)">启用</el-button>
        <el-button type="text" @click="handleClick(scope.row)">实名认证</el-button>
        </template>
    </el-table-column>
  </el-table>
    <div class="foot">
        <el-pagination
                style="float:right;"
                background
            @size-change="handleSizeChange"
            @current-change="handleCurrentChange"
            :current-page="currentPage4"
            :page-sizes="[100, 200, 300, 400]"
            :page-size="100"
            layout="total, sizes, prev, pager, next, jumper"
            :total="400">
            </el-pagination>
    </div>
    <!-- 弹窗 -->
    <el-dialog title="添加交易对" :visible.sync="dialogFormVisible">
    <el-form  :model="form" label-position="top" class="form" :inline="true">
        <el-form-item label="交易币">
            <el-input v-model="form.name"></el-input>
        </el-form-item>
        <el-form-item label="结算币">
            <el-input v-model="form.region"></el-input>
        </el-form-item>
        <el-form-item label="交易币手续费">
            <el-input v-model="form.type"></el-input>
        </el-form-item>
        <el-form-item label="结算币手续费">
            <el-input v-model="form.type"></el-input>
        </el-form-item>
        <el-form-item label="交易币手续费">
            <el-input v-model="form.type"></el-input>
        </el-form-item>
        <el-form-item label="结算币手续费">
            <el-input v-model="form.type"></el-input>
        </el-form-item>
    </el-form>
    <div slot="footer" class="dialog-footer">
        <el-button type="success" @click="dialogFormVisible = false">添 加</el-button>
    </div>
    </el-dialog>
  </div>
</template>

<script>

export default {
  name: 'member',
  data() {
    return {
    dialogFormVisible: false,
    formLabelWidth: '120px',
    form:{},
     options: [{
          value: '选项1',
          label: '黄金糕'
        }, {
          value: '选项2',
          label: '双皮奶'
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
        value: '',
    tableData3: [
        {
            id: '02154215',
          date: '2016-05-03',
          phone: 18483641399,
          autonymState: 'A',
          state: '1',
        },
        {
            id: '02154215',
          date: '2016-05-03',
          phone: 18483641399,
          autonymState: 'B',
          state: '2',
        },
        {
            id: '02154215',
          date: '2016-05-03',
          phone: 18483641399,
          autonymState: 'C',
          state: '1',
        },
        {
            id: '02154215',
          date: '2016-05-03',
          phone: 18483641399,
          autonymState: 'A',
          state: '1',
        },
        {
            id: '02154215',
          date: '2016-05-03',
          phone: 18483641399,
          autonymState: 'C',
          state: '2',
        },
        {
            id: '02154215',
          date: '2016-05-03',
          phone: 18483641399,
          autonymState: 'C',
          state: '2',
        },
        {
            id: '02154215',
          date: '2016-05-03',
          phone: 18483641399,
          autonymState: 'C',
          state: '2',
        },
        {
            id: '02154215',
          date: '2016-05-03',
          phone: 18483641399,
          autonymState: 'C',
          state: '2',
        },
        {
            id: '02154215',
          date: '2016-05-03',
          phone: 18483641399,
          autonymState: 'C',
          state: '2',
        },
        {
            id: '02154215',
          date: '2016-05-03',
          phone: 18483641399,
          autonymState: 'C',
          state: '2',
        },
        {
            id: '02154215',
          date: '2016-05-03',
          phone: 18483641399,
          autonymState: 'C',
          state: '2',
        },
        ],
    }
  },
  computed: {
  },
  created() {
  },
  methods: {
      handleClick(row){

      }
  }
}
</script>
<style>
.tablebox {
    padding: 15px;
    border-top: 1px solid #ebeef5;
}
.search {
    width: 35%;
    display: flex;
    margin: 10px 0 10px 28px;
}
.search>div {
    margin-right: 10px;
}
.foot {
    margin-top: 10px;
    padding: 0 20px;
}
.el-table::before{
    height: 0px;
}
.el-dialog{
    width: 40%;
}
.el-form--inline .el-form-item {
    width: 47%;
}
.el-form--label-top .el-form-item__label {
    padding: 0;
}
.main-container .tags-view-container {
    height: auto;
    padding: 5px 0;
}
form {
    margin-left: 20px;
}
</style>
