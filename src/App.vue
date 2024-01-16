<template>
  <div id="app">
    <FileUpload />
    <FileList />
  </div>
</template>

<script>
import FileUpload from './components/FileUpload.vue';
import FileList from './components/FileList.vue';

export default {
  name: 'App',
  components: {
    FileUpload,
    FileList,
  },
};
</script>
