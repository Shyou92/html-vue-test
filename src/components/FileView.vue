<template>
    <div class="file-background"></div>
    <p class="file">{{name}}</p>
    <p class="file__weight">{{extension + " · " + weight}}</p>
</template>

<script>
export default {
  name: 'FileView',
  props: {
    name: String,
    type: String,
    length: String,
  },
  computed:  {
    extension: function() {
      const regex = /\/[0-9a-z-]{1,}$/;
      const searched = this.type.match(regex)[0];
      const newString = searched.replace("/", '.')
      return newString;
    },
    weight: function() {
      let length = this.length;
      if (parseInt(length) < 1024) {
        return length + ' ' + 'Kb'
      } else {
        return Math.floor(parseInt(length) / 1024) + ' ' + 'Mb'
      }
    }
  }
}
</script>

<style scoped lang="scss">
@import '../assets/templates.scss';

.file{
  color: green;
  @extend %tplfiles;
  text-align: center;
  
  &-background {
    @extend %tplsize;
    margin-top: 40px;
    background-color: lightgreen;
    border: none;
    border-radius: 25%;
  }
  &__weight {
    margin: 5px auto 0;
    opacity: .3;
    line-height: 10px;
    font-size: 14px;
  }
}
</style>
