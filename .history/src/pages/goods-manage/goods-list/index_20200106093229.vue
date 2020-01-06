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
      prop="iDate"
      label="日期"
      width="180">
    </el-table-column>
    <el-table-column
      prop="goodName"
      label="商品名称"
      width="180">
    </el-table-column>
    <el-table-column
      prop="name"
      label="规格"
      width="100">
    </el-table-column>
    <el-table-column
      prop="weightUnits"
      label="单位"
      width="80">
    </el-table-column>
    <el-table-column
      prop="quantity"
      label="数量"
      width="80">
    </el-table-column>
     <el-table-column
      prop="iUnitPrice"
      label="单价"
      width="80">
    </el-table-column>
    <el-table-column
      prop="allPrice"
      label="总额"
      width="100">
    </el-table-column>
    <el-table-column
      prop="desc"
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
                iDate: '2016-05-02',
                goodName: '王小虎',
                desc: '上海市普陀区金沙江路 1518 弄'
                }, {
                iDate: '2016-05-04',
                goodName: '王小虎',
                desc: '上海市普陀区金沙江路 1517 弄'
                }, {
                iDate: '2016-05-01',
                goodName: '王小虎',
                desc: '上海市普陀区金沙江路 1519 弄'
                }, {
                iDate: '2016-05-03',
                goodName: '王小虎',
                desc: '上海市普陀区金沙江路 1516 弄'
            }]
        }
    }
}
</script>
