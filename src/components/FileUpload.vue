<template>
  <div class="m-3">
    <input type="file" class="form-control" @change="uploadFile" />
  </div>
</template>
<script>
export default {
  methods: {
    async uploadFile(event) {
      const file = event.target.files[0];
      if (!file) return;

      const formData = new FormData();
      formData.append('file', file);

      try {
        await fetch('https://your-cloudflare-worker-url/upload', {
          method: 'POST',
          body: formData,
        });
        alert('File uploaded successfully');
      } catch (error) {
        alert('Error uploading file');
      }
    },
  },
};
</script>
