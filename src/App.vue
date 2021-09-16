<template>
  <FolderView name="$"
    :folders="folders" 
    :files="files" 
    :depth="0"
  />
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

</style>
