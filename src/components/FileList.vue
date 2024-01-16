<template>
    <div class="m-3">
      <input type="file" class="form-control" @change="uploadFile" />
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        files: [],
      };
    },
    async created() {
      try {
        const response = await fetch('https://your-cloudflare-worker-url/files');
        if (response.ok) {
          const data = await response.json();
          this.files = data.files;
        } else {
          alert('Error fetching file list');
        }
      } catch (error) {
        alert('Error fetching file list');
      }
    },
  };
  </script>
  