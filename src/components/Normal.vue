<template>
  <div>
    <editor
      v-model="content"
      @init="editorInit"
      lang="html"
      theme="chrome"
      width="100%"
      height="400"
    />
  </div>
</template>

<script>
export default {
  name: "Normal",
  data() {
    return {
      content: "",
    };
  },
  components: {
    editor: require("vue2-ace-editor"),
  },
  methods: {
    editorInit: function () {
      require("brace/ext/language_tools"); //language extension prerequsite...
      require("brace/mode/html");
      require("brace/mode/javascript"); //language
      require("brace/mode/less");
      require("brace/theme/chrome");
      require("brace/snippets/javascript"); //snippet
    },
  },
};
</script>

<style lang="less"></style>
