<template>
  <FolderView name="$" :folders="folders" :files="files" />
</template>

<script>
import FolderView from './components/FolderView.vue'
import data from './data/list';

export default {
  name: 'App',
  components: {
    FolderView
  },
  data: () => data
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  justify-content: center;
  margin: 0 auto;
  height: 60vh;
  width: 60%;
  border: 1px solid black;
}

%tplfolder {
  width: 72px;
  height: 63px;
  background-color: lightblue;
  justify-content: center;
  align-items: center;
  border: none;
  border-radius: 25%;
  cursor: pointer;
  opacity: .7;
}

.folder {
  // display: none;
  @extend %tplfolder;
}

.folder:hover {
  opacity: 1;
  transition: .5s;
}

.folder:nth-child(1) {
  display: flex;
}
</style>
