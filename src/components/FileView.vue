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
@import '../assets/templates.scss';

.file{
  color: green;
  @extend %tplfiles
}
</style>
