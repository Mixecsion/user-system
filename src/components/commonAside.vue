<template>
  <el-menu
    id="menu"
    :router="true"
    :default-active="this.$route.path"
    class="el-menu-vertical-demo"
    background-color=" #65b465"
    text-color="#FFFFFF"
    active-text-color="#326732"
    @open="handleOpen"
    @close="handleClose"
    :collapse="isCollapse"
  >
    <h3>充电预约系统</h3>
    <el-menu-item @click="navigation('/')" index="/">
      <i class="el-icon-odometer" color ="#FFFFFF"></i>
      <span slot="title">充电预约</span>
    </el-menu-item>
    <el-menu-item @click="navigation('/queue')" index="/queue">
      <i class="el-icon-postcard"></i>
      <span slot="title">详单查询</span>
    </el-menu-item>
  </el-menu>
</template>

<style lang="less" scoped>
.el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 200px;
  min-height: 400px;
}
.el-menu-vertical-demo:not(.el-menu--collapse) {
  height: 100%;
  border: none;
  h3 {
    color: #fff;
    text-align: center;
    line-height: 48px;
  }
}
</style>

<script>
export default {
  data() {
    return {
      isCollapse: false,
      menu: [
        {
          path: "/",
          name: "home",
          label: "首页",
          icon: "menu",
          url: "Home/Home",
        },
        {
          path: "/queue",
          name: "queue",
          label: "队列管理",
          icon: "location",
          url: "Queue/Queue",
        },

      ],
    };
  },
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    },
    navigation(path){
      this.$router.push(path)
    }
  },
  computed: {
    noChildren() {
      return this.menu.filter((item) => !item.children);
    },
    hasChildren() {
      return this.menu.filter((item) => item.children);
    },
  },
};
</script>
