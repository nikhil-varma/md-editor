<template>
  <div class="toolbox">
    <button class="tool" @click="togglePreview">
      <i class="fa fa-columns"></i>
    </button>
  </div>
</template>

<script>
export default {
  name: 'Toolbox',
  props: {
    togglePreviewMode: Function,
  },
  created: function() {
    this.isPreviewEnabled = true;
  },
  methods: {
    togglePreview: function() {
      console.log('toggle');
      this.togglePreviewMode();
    },
  },
};
</script>
<style scoped>
.toolbox {
  width: 60px;
  height: 100%;
  background-color: rgb(34 58 82);
  color: white;
  text-align: center;
  line-height: 60px;
  border: none;
  box-shadow: 0 -4px 22px -6px rgb(0 0 0 / 63%);
}
button {
  background: transparent;
  outline: none;
  color: white;
  font-size: 19px;
  border: none;
  cursor: pointer;
  width: 100%;
  height: 70px;
}
button:hover {
  background-color: #132536;
}
</style>
