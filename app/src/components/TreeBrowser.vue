<template >
  <div>
    <div :style="{ 'margin-left': `${depth * 20}px` }" class="node">
      {{ node.name }}
    </div>
    <TreeBrowser
      v-for="child in node.children"
      :key="child.name"
      :node="child"
      :depth="1 + depth"
    />{{ typeof depth  }}
  </div>
</template>
<script>
export default {
  name: "TreeBrowser",
  props: {
    node: Object,
    depth: {
      type: Number,
      dafault: 1,
    },
  },
  data() {
    return {
      expanded: false,
    };
  },
};
</script>
<style scoped>
.node {
  text-align: left;
  font-size: 15px;
}
</style>