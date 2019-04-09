<template>
  <el-container class="container">
    <el-header>
      <el-col :span="4">
        <img src="@/assets/logo.png" alt="图片加载失败">
      </el-col>
      <el-col :span="19" class="middle">
        <h2>电商后台管理系统</h2>
      </el-col>
      <el-col :span="1">
        <div class="grid-content bg-purple">
          <a href="#" @click.prevent="handleLoginout()" class="loginout">退出</a>
        </div>
      </el-col>
    </el-header>
    <el-container>
      <el-aside width="200px">
        <el-menu default-active="1" :router="true" :unique-opened="true">
          <!--     用户管理       -->
          <el-submenu index="1">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span>用户管理</span>
            </template>
            <el-menu-item index="1-1">
              <i class="el-icon-menu"></i>用户列表
            </el-menu-item>
          </el-submenu>
          <!--     权限管理       -->
          <el-submenu index="2" :router="true">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span>权限管理</span>
            </template>
            <el-menu-item index="1-1">
              <i class="el-icon-menu"></i>角色列表
            </el-menu-item>
            <el-menu-item index="1-1">
              <i class="el-icon-menu"></i>权限列表
            </el-menu-item>
          </el-submenu>
          <!--     商品管理       -->
          <el-submenu index="3" :router="true">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span>商品管理</span>
            </template>
            <el-menu-item index="1-1">
              <i class="el-icon-menu"></i>商品列表
            </el-menu-item>
            <el-menu-item index="1-1">
              <i class="el-icon-menu"></i>分类参数
            </el-menu-item>
            <el-menu-item index="1-1">
              <i class="el-icon-menu"></i>商品分类
            </el-menu-item>
          </el-submenu>
          <!--     订单管理       -->
          <el-submenu index="4" :router="true">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span>订单管理</span>
            </template>
            <el-menu-item index="1-1">
              <i class="el-icon-menu"></i>订单列表
            </el-menu-item>
          </el-submenu>
          <!--     数据统计       -->
          <el-submenu index="5" :router="true">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span>数据统计</span>
            </template>
            <el-menu-item index="1-1">
              <i class="el-icon-menu"></i>数据报表
            </el-menu-item>
          </el-submenu>
        </el-menu>
      </el-aside>
      <el-main>Main</el-main>
    </el-container>
  </el-container>
</template>

<script>
export default {
  beforeMount() {
    console.log("hahahzhixingle");
    if (!localStorage.getItem("token")) {
      this.$router.push({
        name: "login"
      });
    }
  },
  methods: {
    handleLoginout() {
      localStorage.clear();
      this.$router.push({
        name: "login"
      });
      this.$message.warning("退出成功");
    }
  }
};
</script>

<style>
.container {
  background: #b3c0d1;
  height: 100%;
}
.el-header {
  background-color: b3c0d1;
  color: #333;
  /* height: 100%; */
  /* text-align: center;
  line-height: 60px; */
}
.middle {
  text-align: center;
  line-height: 60px;
}
h2 {
  color: white;
}
.loginout {
  line-height: 60px;
  text-decoration: none;
}
.el-aside {
  background-color: #fff;
  color: #333;
}

.el-main {
  background-color: #e8edf3;
  color: #333;
}
</style>
