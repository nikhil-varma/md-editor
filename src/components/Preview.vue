<template>
  <div class="preview" v-html="renderedContent"></div>
</template>

<script>
export default {
  name: 'Preview',
  props: {
    renderedContent: String,
  },
};
</script>
<style scoped>
.preview {
  width: 100%;
  height: 100%;
  background-color: #1b2f42;
  color: white;
  overflow-y: scroll;
  padding: 20px;
  box-sizing: border-box;
}
</style>
