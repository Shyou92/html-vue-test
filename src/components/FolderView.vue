<template>
  <p class="folder" 
    @click="toggleChildren"
  >{{name}}</p>
  <template v-for="folder in folders" 
    :key='folder.files.length' 
    :style="indent"
  >
    <FolderView
      v-if="showChildren"
      :name="folder.name" 
      :folders="folder.folders" 
      :files="folder.files"
      :depth="depth + 1"
      v-bind:key="showChildren"
    />
  </template>
  <template v-for="file in files" :key='file.length'>
    <FileView 
      v-if="showChildren"
      :name="file.name"
    />
  </template>
</template>

<script>
import FileView from "./FileView";
export default {
  name: 'FolderView',
  components: {FileView},
  props: {
    name: String,
    folders:Array,
    files:Array,
    depth: Number,
  },
  data() {
    return {
      showChildren: false,
    }
  },
  methods: {
    toggleChildren() {
      this.showChildren = !this.showChildren;
    }
  },
  computed: {
    indent() {
      return { transform: `translate(${this.depth * 50}px)`}
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../assets/templates.scss";

.folder {
  color: orangered;
  @extend %tplfolder;

    &:hover {
    opacity: 1;
    transition: .5s;
  }

}
</style>
