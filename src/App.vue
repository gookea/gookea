<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import HelloWorld from "./components/HelloWorld.vue";
import Base64 from "./components/Base64.vue";
</script>

<template>
  <div class="logo-box">
    <img class="logo vite" src="./assets/vite.svg" />
    <img class="logo electron" src="./assets/electron.svg" />
    <img class="logo vue" src="./assets/vue.svg" />
  </div>
  <el-tabs v-model="activeName" class="demo-tabs" @tab-click="handleClick">
    <el-tab-pane label="Base64" name="Base64">
      <Base64 />
    </el-tab-pane>
    <el-tab-pane label="Config" name="second">Config</el-tab-pane>
    <el-tab-pane label="Role" name="third">Role</el-tab-pane>
    <el-tab-pane label="Hello World" name="fourth">
      <HelloWorld msg="Hello Vue 3 + TypeScript + Vite" />
    </el-tab-pane>
  </el-tabs>
  <div class="static-public">
    Place static files into the <code>/public</code> folder
    <img style="width: 77px" :src="'./node.png'" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import { ElConfigProvider } from "element-plus";
import zhCn from "element-plus/dist/locale/zh-cn.mjs";
import "dayjs/locale/zh-cn";

const activeName = ref("Base64");

export default defineComponent({
  components: {
    ElConfigProvider,
  },
  setup() {
    return {
      size: "large",
      locale: zhCn,
    };
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.logo-box {
  display: flex;
  width: 100%;
  justify-content: center;
}

.static-public {
  display: flex;
  align-items: center;
  justify-content: center;
}

.static-public code {
  background-color: #eee;
  padding: 2px 4px;
  margin: 0 4px;
  border-radius: 4px;
  color: #304455;
}

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: 0.75s;
}

.logo.vite:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.electron:hover {
  filter: drop-shadow(0 0 2em #9feaf9);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
