<template>
  <div class="contents-table">
    <h2>Table Of Contents</h2>
    <ul class="entire-table">
      <li><a href="/">Entire By-law</a></li>
      <li class="preamble"><a href="#preamble">Preamble</a></li>
      <li class="chapter-content" v-bind:key="content.id" v-for="content in contentList">
        <span v-on:click="onIconClick(content.id)" v-bind:class="expand[content.id] ? 'expand rotate' : 'expand'">></span>
        <a :href="'#' + content.id">{{content.title}}</a>
        <ul v-bind:class="expand[content.id] ? 'content-children' : 'no-display'" v-bind:key="child.id" v-for="child in content.children">
            <li><a :href="'#' + child.id">{{child.title}}</a></li>
        </ul>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'TableOfContents',
  props: ["contentList"],
  data(){ 
    return{
      expand: {
        chp_1: false,
        chp_2: false,
        chp_3: false,
        chp_4: false,
        chp_5: false,
        chp_6: false,
        chp_7: false
      }
    }
  },
  methods: {
    onIconClick(id){
      this.expand = {
        ...this.expand,
        [id]: !this.expand[id]
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h2 {
  margin: 50px 0;
}
.chapter-content {
  margin: 40px 0;
}
.preamble {
  margin-top: 40px;
}
ul {
  list-style-type: none;
}
.no-display{
  display: none
}
.contents-table {
  width: 30%;
  padding-left: 30px;
  background-color: #2F2B4A;
  margin: 0;
  color: #F0F4F7;
  height: 100vh;
  position: fixed;
}
.expand  {
  margin-right: 15px;
  display: inline-block;
  font-size: 20px;
  cursor: pointer;
}
.rotate {
  transform: rotate(90deg);
}
.entire-table { 
  height: auto;
  overflow-y: auto;
  max-height: calc(100vh - 9rem);
  margin-top: 20px;
}
.content-children {
  margin: 20px;
  margin-left: 40px;
}
a {
  text-decoration: none;
  color: #F0F4F7;
}
</style>
