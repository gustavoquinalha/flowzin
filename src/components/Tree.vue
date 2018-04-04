<template>
  <div class="role">
    <div class="btn" @click="show">
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
  ],
  methods: {
    show (ev) {
      let el = ev.target.nextElementSibling
      if (el.style.display) el.style.display = null
      else el.style.display = 'none'
    }
  }
}
</script>

<style lang="scss" scoped>
.role {
  box-shadow: 0 0 0 2px blue;
  margin: 10px;
}
.container {
  align-items: flex-start;
  justify-content: center;
}
</style>
