<template>
  <div class="editor">
    <h1>エディター画面</h1>
    <span>{{ user.displayName }}</span>
    <button @click="logout">ログアウト</button>
    <div class="editorWrapper">
      <textarea class="markdown" v-model="markdown"></textarea>
      <div class="preview" v-html="preview()"></div>
    </div>
  </div>
</template>

<script>
import marked from "marked"

export default {
  name: "editor",
  props: ["user"],
  data() {
    return {
      markdown: ""
    }
  },
  methods: {
    logout: function () {
      firebase.auth().signOut()
    },
    preview: function () {
      return marked(this.markdown)
    }
  }
}
</script>

<style lang="scss" scoped>
.editorWrapper {
  display: flex;
}
.markdown {
  width: 50%;
  text-align: left;
}
.preview {
  width: 50%;
  color: #5d627b;
  text-align: left;
  background: white;
  box-shadow: 0 3px 5px rgba(0, 0, 0, 0.22);
}
</style>
