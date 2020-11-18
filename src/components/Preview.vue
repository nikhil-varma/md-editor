<template>
  <div class="preview" v-html="renderedContent"></div>
</template>

<script>
export default {
  name: 'Preview',
  props: {
    renderedContent: HTMLAllCollection,
  },
};
</script>
<style scoped>
.preview {
  width: 100%;
  height: 100%;
  overflow-y: scroll;
  background-color: #1b2f42;
  color: white;
  padding: 20px;
  box-sizing: border-box;
}
</style>
