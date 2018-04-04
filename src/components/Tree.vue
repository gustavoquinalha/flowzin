<template>
  <ul class="role">
    <li>
      <div class="btn" id="box-0">
        {{ text }}
      </div>
      <div class="">
        hover
      </div>
      <div class="container" :class="{ wrap : responsive}">
        <tree v-for="(node, index) in nodes" :nodes="node.childrens" :text="node.text" :key="`${node.text}${index}`" :id="'box-' + (index + 1)" />
      </div>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'tree',
  props: [
    'nodes',
    'text'
  ],
  data () {
    return {
      responsive: false
    }
  }
}
</script>

<style lang="scss" scoped>
.role {
  box-shadow: 0 0 0 2px blue;
  position: relative;
  margin: 10px;
}
// #box-0 {
//   background: $color-primary;
// }
</style>
