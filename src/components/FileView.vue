<template>
  <p class="file">{{name}}</p>
</template>

<script>
export default {
  name: 'FileView',
  props: {
    name: String
  }
}
</script>

<style scoped lang="scss">
.file{
  display: none;
  color: green;
}
</style>
