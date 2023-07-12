<script setup lang="ts">
import Setting from '@/components/settings/Settings.vue'
import PicName from '@/components/picName/PicName.vue'
import FileOperator from '@/components/fileOperator/FileOperator.vue'
</script>

<template>
  <el-container>
    <el-header>
      <div class="left">
        <FileOperator />
      </div>
      <PicName />
      <div class="right">
        <Setting />
      </div>
    </el-header>
    <el-container>

      <el-aside>
        <div class="imageArea"></div>
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
    align-items: center;
    justify-content: space-between;

    height: 35px;
    background-color: rgb(106, 79, 151);

    .left {
      height: inherit;

      display: flex;
      align-items: center;
    }

    .right {
      height: inherit;

      display: flex;
      align-items: center;
    }
  }

  .el-aside {
    width: 75%;
    background-color: #1C1B1C;

    padding: 5px;

    .imageArea {
      height: 100%;
      width: 100%;
      background-color: #292729;
    }
  }
}
</style>
