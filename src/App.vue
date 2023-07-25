<template>
  <div id="app">
    <a-tabs default-active-key="1">
      <a-tab-pane key="1" tab="基础功能">
        <Normal />
      </a-tab-pane>
      <a-tab-pane key="2" tab="封装编辑器">
        <Editor />
      </a-tab-pane>
    </a-tabs>
  </div>
</template>

<script>
import Normal from '@/components/Normal'
import Editor from '@/components/Editor'

export default {
  name: 'App',
  components: {
    Normal,
    Editor,
  }
}
</script>

<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
