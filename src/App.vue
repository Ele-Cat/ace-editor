<template>
  <a-config-provider :locale="locale">
    <div id="app">
      <a-tabs :default-active-key="activeTab">
        <a-tab-pane key="1" tab="基础功能">
          <Normal />
        </a-tab-pane>
        <a-tab-pane key="2" tab="封装编辑器">
          <Editor v-model="content" />
          <a-button type="primary" style="margin:12px 0 0 12px" @click="getCode">获取代码</a-button>
          <a-button type="primary" style="margin:12px 0 0 12px" @click="setCode">设置代码</a-button>
        </a-tab-pane>
      </a-tabs>
    </div>
  </a-config-provider>
</template>

<script>
import zhCN from 'ant-design-vue/lib/locale-provider/zh_CN';
import Normal from "@/components/Normal";
import Editor from "@/components/Editor";

export default {
  name: "App",
  components: {
    Normal,
    Editor,
  },
  data() {
    return {
      locale: zhCN,
      activeTab: "2",
      content: "",
    };
  },
  methods: {
    // 获取代码
    getCode() {
      console.log(this.content);
      const textarea = document.createElement("textarea");
      textarea.value = this.content;
      document.body.appendChild(textarea);
      textarea.select();
      document.execCommand("copy");
      document.body.removeChild(textarea);
      this.$message.success('复制成功')
    },
    setCode() {
      this.content = 'let a = 1;\nconsole.log(a);';
    }
  },
};
</script>

<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
