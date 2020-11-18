<template>
  <div class="editor">
    <Toolbox :togglePreviewMode="togglePreviewMode" />
    <textarea
      class="editor-input"
      v-model="editorInput"
      @input="handleInputChange"
    ></textarea>
  </div>
</template>

<script>
import Toolbox from './Toolbox.vue';

export default {
  name: 'Editor',
  components: {
    Toolbox: Toolbox,
  },
  props: {
    handleEditorInputChange: Function,
    togglePreviewMode: Function,
  },
  data() {
    return {editorInput: ''};
  },
  methods: {
    handleInputChange: function() {
      this.handleEditorInputChange(this.editorInput);
    },
  },
};
</script>

<style scoped>
.editor {
  width: 100%;
  display: flex;
  flex-direction: row;
}
.editor .editor-input {
  width: 100%;
  height: 100%;
  padding: 20px;
  box-sizing: border-box;
  color: white;
  background-color: transparent;
  border: none;
  resize: none;
  outline: none;
  background-color: #132536;
}
</style>
