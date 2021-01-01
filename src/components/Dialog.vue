<template>
    <div class="dialog">
        <el-dialog
            title="添加基金信息"
            :visible.sync="dialog.show"
            :close-click-modal="false"
            :close-on-press-escape="false"
            :modal-append-to-body="false"
        >
            <div class="form">
                <el-form
                  ref="form"
                  :model="formData"
                  :rules="form_rules"
                  label-width="120px"
                  style="margin:10px;width:auto;"
                >
                  <el-form-item label="收支类型:">
                      <el-select v-model="formData.type" placeholder="收支类型">
                          <el-option v-for="(formtype,index) in format_type_list" :key="index" :label="formtype" :value="formtype">
                          </el-option>
                      </el-select>
                  </el-form-item>
                  <el-form-item prop="describe" label="收支描述:">
                      <el-input type="describe" v-model="formData.describe"></el-input>
                  </el-form-item>    
                </el-form>
            </div>
        </el-dialog>
    </div>
</template>

<script>
export default {
    name:'diaLog',
    data(){
        return{
            formData:{
                type:"",
                describe:"",
                income:"",
                expend:"",
                cash:"",
                remark:"",
                id:""
            },
            format_type_list:[
                "提现",
                "提现手续费",
                "充值",
                "优惠券",
                "充值礼券",
                "转账"
            ]
        }
    },
    props:{
        dialog:Object
    }
}
</script>

<style scoped>
    
</style>