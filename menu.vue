<template>
    <div class="menu">

        <el-menu
            class="el-menu-vertical-demo"
            @open="handleOpen"
            @close="handleClose"
            active-text-color="#ffd04b"
            router
            :default-active="defaultActive"
            >

            <template>
                    <el-menu-item index="/">
                        <i class="el-icon-menu"></i>
                        首页
                    </el-menu-item>
            </template>
            
            <el-submenu index="1">

                <template slot="title">
                    <i class="el-icon-setting"></i>
                    <span>系统设置</span>
                </template>

                <el-menu-item-group>
                    <el-menu-item index="/main">菜单管理</el-menu-item>
                </el-menu-item-group>

                <el-menu-item-group>
                    <el-menu-item>角色管理</el-menu-item>
                </el-menu-item-group>

                <el-menu-item-group>
                    <el-menu-item>管理员管理</el-menu-item>
                </el-menu-item-group>

            </el-submenu>

            <el-submenu index="2">

                <template slot="title">
                    <span>商城管理</span>
                </template>

            </el-submenu>
        </el-menu>
    </div>
</template>

<script>
export default {

    methods: {
      handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      }

    },
    data(){
        return {
            defaultActive:""
        }
    },
    //路由地址变化（刷新）
    mounted(){
        this.defaultActive = this.$route.meta.selected
        // console.log(this.$route);
    },

    //路由地址变化（不刷新）
    watch:{

        $route(newVal){
            this.defaultActive = newVal.meta.selected
        }
        
    }
}
</script>

<style lang="stylus" scoped>
    
    .menu
        background-color #ffffff

    .el-menu-item-group__title
        font-size 20px


</style>>

