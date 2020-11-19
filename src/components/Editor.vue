<template>
  <div class="editor">
    <Toolbox :togglePreviewMode="togglePreviewMode" />
    <textarea
      placeholder="Start writing here"
      class="editor-input"
      v-model="editorInput"
      @input="handleInputChange"
      v-on:keydown="handleKeyboardEvent"
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
    handleKeyboardEvent: function(event) {
      const {key, keyCode} = event;
      if (keyCode === 9) {
        event.preventDefault();
        this.editorInput += '  ';
        console.log(key, event.keyCode);
      }
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
  width: calc(100% - 60px);
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
