<template>
  <div class="guanli">
    <el-breadcrumb separator="/">
    <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
    <el-breadcrumb-item :to="{ path:'/main' }">菜单管理</el-breadcrumb-item>
    </el-breadcrumb>
    <el-button type="primary" @click="add">添加</el-button>
    <el-table :data="tableData" style="width: 100%">
      <el-table-column label="菜单编号" prop="id"></el-table-column>
      <el-table-column label="菜单名称" prop="name"></el-table-column>
      <el-table-column label="菜单图标" prop="menuic">
        <template slot-scope="iconFont">
          <i :class="iconFont.row.menuic"></i>
        </template>
      </el-table-column>
      <el-table-column label="菜单地址" prop="address"></el-table-column>
      <el-table-column label="状态">
          <el-button type="primary" @click="check(qiyong)">{{ msg }}</el-button>
      </el-table-column>
      <el-table-column label="操作">
          <el-button type="primary">编辑</el-button>
          <el-button type="danger">删除</el-button>
      </el-table-column>
    </el-table>
    <router-view></router-view>
  </div>
  
</template>

<script>
    export default {
        data(){
            return {
                tableData: [{
                                id: '1',
                                name: '系统设置',
                                menuic: 'el-icon-warning',
                                address: '',
                                qiyong: 1
                            },
                            {
                                id: '2',
                                name: '角色管理',
                                menuic: 'el-icon-s-goods',
                                address: '',
                                qiyong: 0
                            }],
                
                msg:"启用"
            }
        },

        methods:{
            add(){
                this.$router.push({name:"add"})
                // this.$router.push("/main/add")
            },

            check(qiyong){
              if(this.qiyong = 1){
                this.msg = "启用"
                
              }else{
                this.msg = "禁用"
                
              }
            }

        }
    };
</script>

<style>
    .demo-table-expand {
        font-size: 0;
    }
    .demo-table-expand label {
        width: 90px;
        color: #99a9bf;
    }
    .demo-table-expand .el-form-item {
        margin-right: 0;
        margin-bottom: 0;
        width: 50%;
    }
</style>