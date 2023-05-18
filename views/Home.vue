<template>
  <el-container style="height: 100vh">
    <el-aside width="auto">
      <common-aside></common-aside>
    </el-aside>
    <el-container>
      <el-header>
        <common-header></common-header>
      </el-header>
      <el-main>
        <el-row span="8" style="margin-top: 20px" :gutter="20" z-index:2>
          <el-col :span="8">
            <el-card shadow="hover">
              <div class="userinfo">
                <p class="name">当前充电模式：</p>
                <p class="number">本次请求充电量：</p>
                <el-button
                  type="success"
                  class="login-submit"
                  @click="dialogFormVisible = true"
                  >修改预约信息</el-button>
                  <el-dialog title="修改预约信息" :visible.sync="dialogFormVisible">
                    <el-form :model="form">
                      <el-form-item label="充电模式" :label-width="formLabelWidth">
                        <el-select v-model="form.mod" placeholder="请选择充电模式">
                          <el-option label="快充" value="快充"></el-option>
                          <el-option label="慢充" value="慢充"></el-option>
                        </el-select>
                      </el-form-item>
                      <el-form-item label="预约充电量" :label-width="formLabelWidth">
                        <div class="block">
                          <span class="demonstration">(最低100w)</span>
                          <el-slider v-model="form.capa" :format-tooltip="formatTooltip" color =#65b465></el-slider>   
                        </div>                   
                      </el-form-item>
                    </el-form>
                    <div slot="footer" class="dialog-footer">
                      <el-button @click="dialogFormVisible = false">取 消</el-button>
                      <el-button type="success" @click="dialogFormVisible = false">确 定</el-button>
                    </div>
                  </el-dialog>
                <el-divider></el-divider>
              </div>
            </el-card>
          </el-col>
          <el-col :span="4">
            <el-card shadow="hover">
              <div class="userinfo">
                <p class="name">本车排队号码</p>
                <el-divider></el-divider>
              </div>
            </el-card>
          </el-col>
          <el-col :span="4">
            <el-card shadow="hover">
              <div class="userinfo">
                <p class="name">前方等待车辆还有</p>
                <el-divider></el-divider>
              </div>
            </el-card>
          </el-col>
        </el-row>
        <el-row span="8" style="margin-top: 20px" :gutter="20" z-index:2>
          <el-col :span="4">
            <el-card shadow="hover">
              <div class="progress">
                <p class="circle" style="margin">充电进度</p>
                <el-progress type="circle" :percentage="25" color =#65b465></el-progress>
                <el-divider></el-divider>
                <el-button type="success" >结束充电</el-button>
              </div>
            </el-card>
          </el-col>
        </el-row>
      </el-main>
    </el-container>
  </el-container>
</template>

<script>
import CommonAside from "../src/components/commonAside.vue";
import CommonHeader from "../src/components/commonHeader.vue";

export default {
    name: "HomePage",
    components: {
        CommonAside,
        CommonHeader,
    },
    data() {
        return {
        msg: "home here",
        dialogTableVisible: false,
        dialogFormVisible: false,
        form: {
          mod: '',
          capa: '',
        },
        }
    },
    methods:{
      formatTooltip(val) {
        return val / 100;
      }
    }
}
</script>


<style lang="less" scoped>
.el-header {
  background-color: #333;
}
.el-main {
  padding-top: 0;
  background-color: rgb(234, 234, 234);
}
.userinfo {
  background-color: rgb(255, 255, 255);
}
.progress{
  margin: 10px auto 10px auto;
}
</style>