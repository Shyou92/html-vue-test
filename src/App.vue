<template>
<h2 class="header">File Manager 
  <div class="header__wave"></div>
</h2>
<section class="folder-cover">
  <FolderView name="$"
    :folders="folders" 
    :files="files" 
    :depth="0"
  />
</section>
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
@import './assets/normalize.css';

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 0 auto;
  padding: 0;
  width: 100%;
  min-height: 100vh;
  height: 100%;
  background-color: #6893FD;
}

.folder-cover {
  margin-top: 100px;
  width: 40%;
  min-height: 85vh;
  height: 100%;
  background-color: #fff;
  display: flex;
  border: none;
  border-radius: 85px;
  box-shadow: 0 0 10px rgba(0,0,0,0.5);
  flex-direction: column;
  align-items: center;
  padding-bottom: 20px;
  margin-bottom: 20px;
}

.header {
  margin: 0 auto;
  padding: 15px 0 0   0;
  width: 100%;
  text-align: center;
  height: 2em;
  background-color: rgb(134, 225, 255);
  color: white;
  z-index: 3;

  &__wave {
    position: relative;
    height: 25px;
    width: 100%;
    background-color: rgb(134, 225, 255);
    

    &:before {
      content: '';
      display: block;
      position: absolute;
      border-radius: 100% 44%;
      width: 50%;
      height: 96px;
      background-color: #6893FD;
      right: 0;
      top: -7px;
      z-index: 5;
    }

    &:after {
      content: "";
      display: block;
      position: absolute;
      border-radius: 100% 50%;
      width: 60%;
      height: 90px;
      background-color: rgb(134, 225, 255);
      left: -60px;
      top: -22px;
      z-index: -1;
    }
  }
}

</style>
