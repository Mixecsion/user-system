<template>
  <header>
    <div class="r-content">
      <el-dropdown trigger="click" size="small">
        <span>
          <img class="user" :src=userImg />
        </span>
        <el-dropdown-menu slot="dropdown">
          <el-dropdown-item @click="this.$router.push('login')" index="/login"
            >退出</el-dropdown-item
          >
        </el-dropdown-menu>
      </el-dropdown>
    </div>
  </header>
</template>

<script>
export default{
    name:"CommonHeader",
    data(){
        return{
          userImg: require('../assets/充电站.png')
        }
    },
    methods:{
    }
}
</script>
<style lang="less" scoped>
header {
  display: flex;
  height: 100%;
  justify-content: flex-end;
  align-items: center;
}
.r-content {
  .user {
    width: 30px;
    height: 30px;
    border-radius: 50%;
  }
}
</style>
