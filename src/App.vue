<script setup lang="ts">
import Setting from '../src/components/settings/Settings.vue'
</script>

<template>
  <el-container>
    <el-header>
      Header content
      <div class="right">
        <Setting></Setting>
      </div>
    </el-header>
    <el-container>
      <el-aside>
        Aside content
      </el-aside>

      <el-main>
        Main content
      </el-main>
    </el-container>
  </el-container>
</template>

<style scoped lang="scss">
.el-container {
  height: 100%;

  .el-header {
    display: flex;


    height: 35px;
    background-color: rgb(106, 79, 151);

    .right {}
  }

  .el-aside {
    width: 75%;
    background-color: lightblue;
  }
}
</style>
