<template>
  <div class="add">
    <el-breadcrumb separator="/">
      <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
      <el-breadcrumb-item :to="{ path: '/main' }">菜单管理</el-breadcrumb-item>
      <el-breadcrumb-item :to="{ path: '/main/add' }">数据追加</el-breadcrumb-item>
    </el-breadcrumb>
    <el-form ref="form" :model="form" label-width="80px">
      <el-form-item label="菜单名称">
        <el-input v-model="form.name"></el-input>
      </el-form-item>
      <el-form-item label="菜单类型">
        <el-radio v-model="form.radio" label="1">目录</el-radio>
        <el-radio v-model="form.radio" label="2">菜单</el-radio>
      </el-form-item>
      <el-form-item label="上级菜单">
        <el-select v-model="form.up" placeholder="请选择">
          <el-option label="区域一" value="shanghai"></el-option>
          <el-option label="区域二" value="beijing"></el-option>
        </el-select>
      </el-form-item>
      <el-form-item label="菜单图标">
        <el-input v-model="form.icon"></el-input>
       </el-form-item>
      <el-form-item label="状态">
        <el-switch v-model="form.status"></el-switch>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="">添加</el-button>
        <el-button type="primary" @click="go(-1)">返回</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: "",
        radio: "1",
        up:"",
        icon: "",
        status:false
        
      },
    };
  },
  methods: {
    onSubmit() {
      console.log("submit!");
    },
  },
};
</script>

    

<style>
</style>