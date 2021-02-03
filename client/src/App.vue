<template>
  <div id="app">
    <NavigationHeader />
    <div class="app-side-bar">
      <TableOfContents />
    </div>
    <Contents />
  </div>
</template>

<script>
import TableOfContents from './components/TableOfContents.vue';
import Contents from "./components/Contents";
import NavigationHeader from "./components/Navigation/NavigationHeader";

export default {
  name: 'App',
  components: {
    TableOfContents,
    Contents,
    NavigationHeader
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: 'Lato', sans-serif!important;
}
.app-side-bar {
  display: block;
}
@media screen and (max-width: 800px) {
  #app {
    margin: 0 auto;
  }
  .app-side-bar {
    display: none;
  }
}
</style>
