<template>
  <div id="app">
    <TreeBrowser  
    :node="root" 
    @onClick='nodeWasClicked'
    />
  </div>
</template>

<script>
import TreeBrowser from "./components/TreeBrowser.vue";

export default {
  name: "App",
  data() {
    return {
      root: {
        name: "/",
        children: [
          {
            name: "music",
            children: [
              {
                name: "song.mp3",
              }
            ]
          },
          {
            name: "work space",
            children: [
              {
                name: "sourse.js",
              }
            ]
          }
        ]
      }
    }
  },
  methods: {
    nodeWasClicked(node) {
      console.log('1234')
      alert(node.name)
    }
  },
  components: {
    TreeBrowser
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
