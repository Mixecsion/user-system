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
        <el-table
          :data="tableData"
          border
          style="width: 100%">
          <el-table-column
            fixed
            prop="note1"
            label="详单编号"
            width="150">
          </el-table-column>
          <el-table-column
            prop="time"
            label="生成时间"
            width="150">
          </el-table-column>
          <el-table-column
            prop="note2"
            label="充电桩编号"
            width="120">
          </el-table-column>
          <el-table-column
            prop=""
            label="充电电量"
            width="120">
          </el-table-column>
          <el-table-column
            prop="all-time"
            label="充电时长"
            width="120">
          </el-table-column>
          <el-table-column
            prop="start-time"
            label="启动时间"
            width="150">
          </el-table-column>
          <el-table-column
            prop="end-time"
            label="停止时间"
            width="150">
          </el-table-column>
          <el-table-column
            prop="address"
            label="充电费用"
            width="150">
          </el-table-column>
          <el-table-column
            prop="address"
            label="服务费用"
            width="150">
          </el-table-column>
          <el-table-column
            prop="address"
            label="总费用"
            width="150">
          </el-table-column>
          <el-table-column
            fixed="right"
            label="操作"
            width="100">
            <template slot-scope="scope">
              <el-button @click="handleClick(scope.row)" type="text" size="small">缴费</el-button>
            </template>
          </el-table-column>
        </el-table>
      </el-main>
    </el-container>
  </el-container>
</template>

<script>
import CommonAside from "../src/components/commonAside.vue";
import CommonHeader from "../src/components/commonHeader.vue";

export default {
    name: "QueuePage",
    components: {
        CommonAside,
        CommonHeader,
    },
    data() {
        return {
        msg: "queue here",
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
</style>