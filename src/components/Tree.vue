<template>
  <div class="role btn">
    <div>
      {{ text }}
    </div>
    <tree v-for="(node, index) in nodes" :nodes="node.childrens" :text="node.text" :key="`${node.text}${index}`"/>
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
  border: 5px solid blue;
}
</style>
