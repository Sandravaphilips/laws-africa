<template>
  <div class="hello">
    <p>Entire By-law</p>
    <p>Preamble</p>
    <div v-bind:key="content.id" v-for="content in contentList">
        <p>{{content.title}}</p>
        <div v-bind:key="child.id" v-for="child in content.children">
            <p>{{child.title}}</p>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TableOfContents',
  props: ["contentList"]
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
