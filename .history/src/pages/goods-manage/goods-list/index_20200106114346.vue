<template>
  <div class="demo-image__placeholder">
    <div class="block">
      <!-- <el-image :src="src">
      <div slot="placeholder" class="image-slot">
        加载中<span class="dot">...</span>
      </div>
    </el-image> -->
    <div>
        <el-button type="primary" @click="handelAdd">新增</el-button>
    </div>
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
  <el-dialog
  title="提示"
  :visible.sync="dialogVisible"
  width="30%"
  :before-close="handleClose">
  <el-form ref="form" :model="form" label-width="80px">
  <el-form-item label="活动名称">
    <el-input v-model="form.name"></el-input>
  </el-form-item>
  <el-form-item label="活动区域">
    <el-select v-model="form.region" placeholder="请选择活动区域">
      <el-option label="区域一" value="shanghai"></el-option>
      <el-option label="区域二" value="beijing"></el-option>
    </el-select>
  </el-form-item>
  <el-form-item label="活动时间">
    <el-col :span="11">
      <el-date-picker type="date" placeholder="选择日期" v-model="form.date1" style="width: 100%;"></el-date-picker>
    </el-col>
    <el-col class="line" :span="2">-</el-col>
    <el-col :span="11">
      <el-time-picker placeholder="选择时间" v-model="form.date2" style="width: 100%;"></el-time-picker>
    </el-col>
  </el-form-item>
  <el-form-item label="即时配送">
    <el-switch v-model="form.delivery"></el-switch>
  </el-form-item>
  <el-form-item label="活动性质">
    <el-checkbox-group v-model="form.type">
      <el-checkbox label="美食/餐厅线上活动" name="type"></el-checkbox>
      <el-checkbox label="地推活动" name="type"></el-checkbox>
      <el-checkbox label="线下主题活动" name="type"></el-checkbox>
      <el-checkbox label="单纯品牌曝光" name="type"></el-checkbox>
    </el-checkbox-group>
  </el-form-item>
  <el-form-item label="特殊资源">
    <el-radio-group v-model="form.resource">
      <el-radio label="线上品牌商赞助"></el-radio>
      <el-radio label="线下场地免费"></el-radio>
    </el-radio-group>
  </el-form-item>
  <el-form-item label="活动形式">
    <el-input type="textarea" v-model="form.desc"></el-input>
  </el-form-item>
  <el-form-item>
    <el-button type="primary" @click="onSubmit">立即创建</el-button>
    <el-button>取消</el-button>
  </el-form-item>
</el-form>
</el-dialog>
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
            }],
            dialogVisible: true,
        }
    },
    methods:{
        handelAdd(){
            console.log('新增---')
            this.dialogVisible = true;
        },
        handleClose(done) {
          this.dialogVisible = false;
        }
    }
}
</script>
