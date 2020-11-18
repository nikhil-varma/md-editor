<template>
  <div class="md-editor">
    <Editor
      :handleEditorInputChange="handleEditorInputChange"
      :togglePreviewMode="togglePreviewMode"
    />
    <Preview :renderedContent="previewContent" v-if="isPreviewModeEnabled" />
  </div>
</template>

<script>
import Editor from './components/Editor.vue';
import Preview from './components/Preview.vue';
import marked from 'marked';

export default {
  name: 'App',
  components: {
    Editor: Editor,
    Preview: Preview,
  },
  methods: {
    handleEditorInputChange: function(val) {
      this.previewContent = marked(val);
    },
    togglePreviewMode: function() {
      this.isPreviewModeEnabled = !this.isPreviewModeEnabled;
    },
  },
  data() {
    return {
      previewContent: '',
      isPreviewModeEnabled: true,
    };
  },
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  border-radius: 10px;
}

::-webkit-scrollbar-thumb {
  border-radius: 10px;
  background-color: rgba(219, 219, 219, 0.295);
}
.md-editor {
  display: flex;
  width: 100%;
  height: 100vh;
  margin: 0;
  padding: 0;
  flex-direction: row;
  position: relative;
}
pre {
  background: #43709a9c;
  padding: 8px 8px;
  border-radius: 4px;
}
code {
  background: #43709a9c;
  padding: 3px 4px;
  border-radius: 4px;
}
pre > code {
  background-color: transparent;
}
a {
  color: #27c2ff;
}
blockquote {
  border-left: 10px solid rgb(234, 234, 234, 0.58);
  margin-left: 10px;
  padding-left: 10px;
  padding-top: 1px;
  padding-bottom: 2px;
  border-radius: 3px;
  background-color: #345678;
}
table {
  border: 1px solid rgb(234, 234, 234, 0.35);
}
thead {
  background: #345678;
  height: 40px;
  text-align: left;
  border-right: 1px solid #eaeaea;
}
tr {
  height: 30px;
  line-height: 30px;
}
th,
td {
  padding: 0 20px;
}
</style>
