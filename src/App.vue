<template>
  <div id="app">
    <el-header>
      <span>GO™ ADMIN</span>
      <span class="btn-menu-col" v-on:click="handleMenu"> | 菜单 </span>
      <ul class="header-operations">
        <li>切换主题色</li>
        <li class="header-download">下载主题</li>
        <li>帮助</li>
        <li>
          <span class="header-lang is-active">中文</span>
          <span>/</span>
          <span class="header-lang">En</span>
        </li>
      </ul>
    </el-header>
    <el-container>
      <el-aside>
        <el-menu :default-active="$route.path"  class="el-menu-list" :collapse="isCollapse" :collapse-transition="false" router>
            <el-menu-item index="/home">
                <i class="el-icon-menu"></i>
                <span slot="title">首页</span>
              </el-menu-item>
              <el-menu-item index="/list">
                  <i class="el-icon-tickets"></i>
                  <span slot="title">数据列表</span>
                </el-menu-item>
          <el-submenu index="1">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span slot="title">导航一</span>
            </template>
            <el-menu-item index="1-1">选项1</el-menu-item>
            <el-menu-item index="1-2">选项2</el-menu-item>
            <el-menu-item index="1-3">选项3</el-menu-item>
            <el-submenu index="1-4">
              <span slot="title">选项4</span>
              <el-menu-item index="1-4-1">选项1</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-menu-item index="2">
            <i class="el-icon-goods"></i>
            <span slot="title">导航二</span>
          </el-menu-item>
          <el-menu-item index="3">
            <i class="el-icon-picture"></i>
            <span slot="title">导航三</span>
          </el-menu-item>
          <el-menu-item index="4">
            <i class="el-icon-setting"></i>
            <span slot="title">导航四</span>
          </el-menu-item>
        </el-menu>
      </el-aside>
      <el-main>
        <el-breadcrumb separator="/">
          <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
          <el-breadcrumb-item>
            <a href="/">活动管理</a>
          </el-breadcrumb-item>
          <el-breadcrumb-item>活动列表</el-breadcrumb-item>
          <el-breadcrumb-item>活动详情</el-breadcrumb-item>
        </el-breadcrumb>
        <router-view/>
      </el-main>
    </el-container>
  </div>
</template>
<script>
  export default {
    name: "App",
    data() {
      return {
        isCollapse: false
      };
    },
    methods: {
      handleMenu() {
        this.isCollapse = !this.isCollapse;
      }
    }
  };
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    font-size: 12px;
  }

  html,
  body {
    height: 100%;
  }

  #app {
    font-family: "Avenir", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    height: 100%;
  }

  .el-header {
    background-color: rgb(64, 158, 255);
    color: #fff;
    line-height: 60px;
    padding: 0 20px;
  }

  .btn-menu-col{
    cursor: pointer;
  }

  .header-operations {
    display: inline-block;
    float: right;
    height: 100%;
    font-size: 14px;
  }

  .header-operations li {
    display: inline-block;
    padding: 0 20px;
    line-height: 60px;
    cursor: pointer;
  }

  .el-container {
    display: -webkit-flex;
    display: flex;
  }

  .el-aside {
    width: auto !important;
  }

  .el-menu-list:not(.el-menu--collapse) {
    width: 200px;
    min-height: 400px;
  }

  .el-main {
    flex: 1;
    padding: 15px;
    min-width: 200px;
  }

  .el-breadcrumb{
    margin-bottom: 20px;
  }

  .el-form-item__label {
    font-size: 12px !important;
  }
</style>