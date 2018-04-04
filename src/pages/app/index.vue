<template>
<div class="app container align-center text-align-center">

  <div class="app-content" v-for="(node, index) in nodes" :key="`${node.text}${index}`" v-bind:ref="node.first?'role':''">

    <tree :text="node.text" :nodes="node.childrens"/>

  </div>

</div>
</template>

<script>
import Tree from '@/components/Tree'

export default {
  data () {
    return {
      nodes: [{
        text: 'Father',
        first: true,
        childrens: [
          {
            text: 'Child'
          },
          {
            text: 'Child1',
            childrens: [
              {
                text: 'Child12'
              },
              {
                text: 'Child13',
                childrens: [
                  {
                    text: 'Child234'
                  },
                  {
                    text: 'Child245'
                  }
                ]
              }
            ]
          },
          {
            text: 'Child2'
          },
          {
            text: 'Child3'
          }
        ]
      }]
    }
  },
  components: {
    Tree
  },
  mounted () {
    const div = this.$refs['role'][0]
    console.log(div)

    window.scrollTo((div.offsetLeft / 2), (div.offsetTop - 100))
  }
}
</script>

<style lang="scss" scoped>
.app {
    min-width: 200vw;
    min-height: 200vh;
    background: red;
    padding: 100px;
}
</style>
