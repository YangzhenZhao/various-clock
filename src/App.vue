<template>
  <div id="app">
    <el-tabs v-model="activeName">
      <el-tab-pane label="闹钟" name="alarm">
        <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
        闹钟
      </el-tab-pane>
      <el-tab-pane label="番茄钟" name="tomato">番茄钟</el-tab-pane>
      <el-tab-pane label="时钟" name="clock">
        <clock />
      </el-tab-pane>
      <el-tab-pane label="秒表" name="stopwatch">秒表</el-tab-pane>
      <el-tab-pane label="计时" name="timing">计时</el-tab-pane>
    </el-tabs>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Clock from './components/Clock.vue'
import { ref } from 'vue'
export default {
  name: 'App',
  components: {
    // HelloWorld
    Clock
  },
  setup () {
    const activeName = ref('clock')
    return {
      activeName
    }
  }
}
</script>

<style>
#app {
    text-align: center;
    margin: 0 1em;
}
</style>
