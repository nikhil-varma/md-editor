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
.md-editor {
  display: flex;
  width: 100%;
  height: 100vh;
  margin: 0;
  padding: 0;
  flex-direction: row;
  position: relative;
}
</style>
