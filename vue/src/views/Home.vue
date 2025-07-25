<template>
  <div>
    <div class="card" style="margin-bottom: 5px">
    <el-input style="width: 260px;margin-right: 8px" v-model="input" placeholder="请输入名称查询" :prefix-icon="Search"></el-input>
    <el-button type="primary">查 询</el-button>
    </div>
    <div class="card" style="margin-bottom: 5px">
      <el-button type="danger">批量删除</el-button>
      <el-button type="primary">新增</el-button>
      <el-button type="success">批量导入</el-button>
      <el-button type="info">批量导出</el-button>
    </div>
    <div class="card" style="margin-bottom: 5px">
      <el-table :data="data.tableData" style="width: 100%" :header-cell-style="{color: '#333',backgroundColor:'#eaf4ff'}">
        <el-table-column prop="name" label="名称" width="180" />
        <el-table-column prop="phone" label="电话" />
        <el-table-column prop="address" label="地址" width="180" />
      </el-table>
    </div>
    <div class="card" style="margin-bottom: 5px">
      <el-pagination
          v-model:current-page="data.pageNum"
          :page-size="data.pageSize"
          layout="total, prev, pager, next"
          :total="data.total"
          @size-change="handleSizeChange"
          @current-change="handleCurrentChange"
      />
    </div>
  </div>
</template>

<script setup>
import { reactive } from "vue";
import { Search } from "@element-plus/icons-vue";

const data = reactive({
  tableData: [
    { name: "张三", phone: "123456789", address: "北京" },
    { name: "李四", phone: "987654321", address: "上海" },
    { name: "王五", phone: "111111111", address: "广州" },
    { name: "赵六", phone: "222222222", address: "深圳" },
    { name: "钱七", phone: "333333333", address: "杭州" },
    { name: "孙八", phone: "444444444", address: "南京" },
    { name: "周九", phone: "555555555", address: "武汉" },
    { name: "吴十", phone: "666666666", address: "成都" },
  ],
  name:null,
  pageNum:1,
  pageSize:5,
  total:6,
})
</script>

