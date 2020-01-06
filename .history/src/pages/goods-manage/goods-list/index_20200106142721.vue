<template>
  <div class="demo-image__placeholder">
    <div class="block">
      <!-- <el-image :src="src">
      <div slot="placeholder" class="image-slot">
        加载中<span class="dot">...</span>
      </div>
    </el-image> -->
      <div>
        <el-button type="primary"
                   @click="handelAdd">新增</el-button>
      </div>
      <el-table :data="tableData"
                border
                style="width: 100%">
        <el-table-column prop="iDate"
                         label="日期"
                         width="180">
        </el-table-column>
        <el-table-column prop="goodName"
                         label="商品名称"
                         width="180">
        </el-table-column>
        <el-table-column prop="size"
                         label="规格"
                         width="100">
        </el-table-column>
        <el-table-column prop="weightUnits"
                         label="单位"
                         width="80">
        </el-table-column>
        <el-table-column prop="quantity"
                         label="数量"
                         width="80">
        </el-table-column>
        <el-table-column prop="iUnitPrice"
                         label="单价"
                         width="80">
        </el-table-column>
        <el-table-column prop="allPrice"
                         label="总额"
                         width="100">
        </el-table-column>
        <el-table-column prop="desc"
                         label="备注">
        </el-table-column>
      </el-table>
      <el-dialog title="新增数据"
                 :visible.sync="dialogVisible"
                 width="60%"
                 :before-close="handleClose">
        <el-form ref="form"
                 :model="form"
                 label-width="80px">
          <el-form-item label="商品名称">
            <el-input v-model="form.goodName"></el-input>
          </el-form-item>
          <el-form-item label="入库时间">
            <el-col :span="11">
              <el-date-picker type="date"
                              placeholder="选择日期"
                              v-model="form.iDate"
                              style="width: 100%;"></el-date-picker>
            </el-col>
          </el-form-item>
          <el-form-item label="规格">
            <el-input v-model="form.size"></el-input>
          </el-form-item>
          <el-form-item label="单位">
            <el-input v-model="form.weightUnits"></el-input>
          </el-form-item>
          <el-form-item label="数量">
            <el-input v-model="form.quantity"></el-input>
          </el-form-item>
          <el-form-item label="单价">
            <el-input v-model="form.iUnitPrice"></el-input>
          </el-form-item>
          <el-form-item label="总额">
            <el-input v-model="form.allPrice"></el-input>
          </el-form-item>
          <el-form-item label="备注">
            <el-input type="textarea"
                      v-model="form.desc"></el-input>
          </el-form-item>
          <el-form-item>
            <el-button type="primary"
                       @click="onSubmit">立即创建</el-button>
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
            tableData: [
                {
                    iDate: '2016-05-02',
                    goodName: '王小虎',
                    desc: '上海市普陀区金沙江路 1518 弄'
                },
                {
                    iDate: '2016-05-04',
                    goodName: '王小虎',
                    desc: '上海市普陀区金沙江路 1517 弄'
                },
                {
                    iDate: '2016-05-01',
                    goodName: '王小虎',
                    desc: '上海市普陀区金沙江路 1519 弄'
                },
                {
                    iDate: '2016-05-03',
                    goodName: '王小虎',
                    desc: '上海市普陀区金沙江路 1516 弄'
                }
            ],
            dialogVisible: true,
            form: {
                goodName: '原始橡胶',
                size: '块状',
                weightUnits: '公斤',
                quantity: '1000',
                iDate: '2020-01-01',
                iUnitPrice: '10000',
                allPrice: '10000000',
                desc: '已经结清'
            }
        }
    },
    methods: {
        handelAdd() {
            console.log('新增---')
            this.dialogVisible = true
        },
        handleClose(done) {
            this.dialogVisible = false
        },
        onSubmit() {
            console.log('submit!')
        },
        async handelsubmit() {
            try {
                let data = await addInGood(this.form)
                console.log("新增数据",data)
                // let token = data.token
                // this.$store.commit('LOGIN_IN', token)
                // this.$router.replace('/')
            } catch (e) {
                console.log(e)
            }
        }
    }
}
</script>
