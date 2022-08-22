<template>
  <div>
    <CKEditorVue />
  </div>
</template>

<script>
import CKEditorVue from './components/CKEditor.vue';
export default {
  name: 'App',
  components: {
    CKEditorVue,
  }
}
</script>

<style>
#app {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
