<template>
  <ul class="role">
    <li>
      <div class="btn" :id="`box-${registerId}`">
        {{ text }}
      </div>
      <div class="">
        hover
      </div>
      <div class="container" :class="{ wrap : responsive}">
        <tree v-for="(node, index) in nodes" :nodes="node.childrens" :text="node.text" :key="`${node.text}${index}`" :id="'box-' + (index + 1)" :registerId="`${index}${text}`"/>
      </div>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'tree',
  props: [
    'nodes',
    'text',
    'registerId'
  ],
  data () {
    return {
      responsive: false
    }
  }
}
</script>

<style lang="scss" scoped>
.app-master {
  .role {
    box-shadow: 0 0 0 2px blue;
    position: relative;
    margin: 10px;
  }
}
#box-father {
  background: $color-primary;
  color: #fff;
}
</style>
