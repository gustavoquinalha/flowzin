<template>
  <div class="role">
    <div class="btn">
        {{ text }}
    </div>
    <div class="container wrap">
      <tree v-for="(node, index) in nodes" :nodes="node.childrens" :text="node.text" :key="`${node.text}${index}`"/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'tree',
  props: [
    'nodes',
    'text'
  ]
}
</script>

<style>
.role {
  box-shadow: 0 0 0 2px blue;
  margin: 10px;
}
.container {
  align-items: flex-start;
  justify-content: center;
}
</style>
