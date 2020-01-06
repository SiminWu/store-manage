<template>
  <div class="demo-image__placeholder">
    <div class="block">
      <!-- <el-image :src="src">
      <div slot="placeholder" class="image-slot">
        加载中<span class="dot">...</span>
      </div>
    </el-image> -->
    <el-table
    :data="tableData"
    border
    style="width: 100%">
    <el-table-column
      prop="date"
      label="日期"
      width="180">
    </el-table-column>
    <el-table-column
      prop="name"
      label="商品名称"
      width="180">
    </el-table-column>
    <el-table-column
      prop="name"
      label="规格"
      width="180">
    </el-table-column>
    <el-table-column
      prop="name"
      label="单位"
      width="180">
    </el-table-column>
    <el-table-column
      prop="name"
      label="数量"
      width="180">
    </el-table-column>
     <el-table-column
      prop="name"
      label="单价"
      width="180">
    </el-table-column>
    <el-table-column
      prop="name"
      label="总额"
      width="180">
    </el-table-column>
    <el-table-column
      prop="address"
      label="备注">
    </el-table-column>
  </el-table>
    </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            tableData: [{
                date: '2016-05-02',
                name: '王小虎',
                address: '上海市普陀区金沙江路 1518 弄'
                }, {
                date: '2016-05-04',
                name: '王小虎',
                address: '上海市普陀区金沙江路 1517 弄'
                }, {
                date: '2016-05-01',
                name: '王小虎',
                address: '上海市普陀区金沙江路 1519 弄'
                }, {
                date: '2016-05-03',
                name: '王小虎',
                address: '上海市普陀区金沙江路 1516 弄'
            }]
        }
    }
}
</script>
