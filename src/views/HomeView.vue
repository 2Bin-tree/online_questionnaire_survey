<template>
  <div style="background-color: #f7f7f7">
    <el-container style="height: 100vh;">
      <el-aside class="left-aside">
        <el-col :span="12" style="margin-top: 30vh">
          <el-menu
              default-active="2"
              class="el-menu-vertical-demo"
              @open="handleOpen"
              @close="handleClose"
          >
            <el-menu-item index="1">
              <el-icon>
                <House/>
              </el-icon>
              <span>主页</span>
            </el-menu-item>
            <el-menu-item index="2">
              <el-icon>
                <DocumentAdd/>
              </el-icon>
              <span>设计问卷</span>
            </el-menu-item>
            <el-menu-item index="3">
              <el-icon>
                <Promotion/>
              </el-icon>
              <span>发送问卷</span>
            </el-menu-item>
            <el-menu-item index="4">
              <el-icon>
                <DataAnalysis/>
              </el-icon>
              <span>分析&下载</span>
            </el-menu-item>
          </el-menu>
        </el-col>
      </el-aside>
      <el-container>
        <el-header style="margin-left: 0;margin-top: 0;background-color: white">
          <div style="position: relative">
            <el-menu
                :default-active="activeIndex"
                class="el-menu-demo"
                mode="horizontal"
                @select="handleSelect"
            >
              <el-menu-item index="1">设计向导</el-menu-item>
              <el-menu-item index="2">编辑问卷</el-menu-item>
              <el-menu-item index="3">问卷设置</el-menu-item>
              <el-menu-item index="4">问卷外观</el-menu-item>
              <el-menu-item index="5">红包&奖品</el-menu-item>
              <el-menu-item index="6">质量控制</el-menu-item>
              <el-menu-item index="7">流程审批</el-menu-item>
            </el-menu>
            <el-button type="success" plain style="position: absolute;top: 1.5vh;right: 2vh">Success</el-button>
          </div>
        </el-header>
        <el-main>
          <div class="main-container">
            <div
                style="width: 100vh;
                height: 10vh;
                background-color: #F0F2F5;
                text-align: center;
                margin: 10px;
                display: flex;
                align-items: center">
              <el-icon style="margin-left: 2vh">
                <Loading/>
              </el-icon>
              <span style="margin-left: 1vh">此问卷处于草稿状态，如果您的<span
                  style="font-weight: bold">问卷准备就绪</span>，您可以</span>
              <el-button type="warning" plain style="margin-left: 1vh">发布此问卷</el-button>
            </div>
            <div
                style="width: 100vh;
                height: 10vh;
                background-color: #F0F2F5;
                text-align: center;
                margin: 10px;
                display: flex;
                align-items: center">
              <el-icon style="margin-left: 2vh">
                <Filter/>
              </el-icon>
              <span style="margin-left: 1vh;font-weight: bold">筛选与配置</span>
            </div>
            <div
                style="width: 100vh;
                height: 10vh;
                background-color: #F0F2F5;
                text-align: center;
                margin: 10px;
                display: flex;
                align-items: center">
              <el-icon style="margin-left: 2vh">
                <User/>
              </el-icon>
              <span style="margin-left: 1vh;font-weight: bold">将答题者保存为联系人</span>
              <!--              <el-button type="warning" plain style="margin-left: 1vh">发布此问卷</el-button>-->
            </div>
            <div
                style="width: 100vh;
                height: 10vh;
                background-color: #F0F2F5;
                text-align: center;
                margin: 10px;
                display: flex;
                align-items: center">
              <el-link type="primary" style="margin-left: 3vh;font-weight: bold">编辑问卷  >></el-link>
            </div>
          </div>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script lang="js" setup>
import {ref} from 'vue';

const activeIndex = ref('1');
ref('1');
const handleSelect = (key, keyPath) => {
  console.log(key, keyPath);
};

import {
  House, DocumentAdd, DataAnalysis, Promotion, Loading, User, Filter,
} from '@element-plus/icons-vue';

const handleOpen = (key, keyPath) => {
  console.log(key, keyPath);
};

const handleClose = (key, keyPath) => {
  console.log(key, keyPath);
};

</script>

<style scoped>
.left-aside {
  width: auto;
  margin-left: 0;
  margin-top: 0;
  background-color: white;
}

.el-menu-vertical-demo {
  width: fit-content;
}

.main-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 70vh;
}

.centered-box {
  width: 100vh;
  height: 10vh;
  background-color: #F0F2F5;
  text-align: center;
  line-height: 10vh;
  margin: 10px;
}


</style>