<template>
  <div style="background-color: #f7f7f7">
    <el-container style="height: 100vh;position: relative">
      <el-header style="margin-left: 0;margin-top: 0;background-color: white;height: 5vh">
        <span style="font-weight: bold">问卷编辑</span>
        <el-button type="primary" style="position: absolute; right: 17vh">预览</el-button>
        <el-button type="info" style="position: absolute; right: 4vh">完成编辑</el-button>
      </el-header>
      <el-main style="display: flex;flex-direction: row;justify-content: space-around">
        <div style="width: 20vh;height: 20vh;background-color: white;display: flex;flex-direction: column;justify-content: center">
          <span>新增</span>
          <el-row>
            <el-col style="margin-top: 10px">
              <el-button type="primary">单选</el-button>
            </el-col>
            <el-col style="margin-top: 10px">
              <el-button type="primary">多选</el-button>
            </el-col>
            <el-col style="margin-top: 10px">
              <el-button type="primary">填空</el-button>
            </el-col>
          </el-row>
        </div>
        <div style="width: 120vh;background-color: white">
          b
        </div>
      </el-main>
    </el-container>
  </div>
</template>

<script setup>
</script>

<style scoped>
</style>