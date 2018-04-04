<template>

<div class="">
  <button type="button" name="button" @click="resetPosition()" class="btn btn-reset">reset</button>

  <div class="app container align-center text-align-center" id="appc">
    <div class="app-master" ref="appmaster">
      <div class="app-content" ref="role">
        <tree :text="father.text" :nodes="father.childrens" ref="role"/> </div>
    </div>
  </div>

</div>
</template>

<script>
import Tree from '@/components/Tree'
export default {
  data () {
    return {
      father: {
        text: 'Bichinhos',
        first: true,
        childrens: [
          {
            text: 'Home'
          },
          {
            text: 'Features',
            childrens: [
              {
                text: 'Feature 1'
              },
              {
                text: 'Feature 2',
                childrens: [
                  {
                    text: 'Feature 2 1'
                  },
                  {
                    text: 'Feature 2 2'
                  }
                ]
              }
            ]
          },
          {
            text: 'Mapa'
          },
          {
            text: 'Contato'
          }
        ]

      }
    }
  },
  components: {
    Tree
  },
  mounted () {
    this.resetPosition()
  },
  methods: {
    resetPosition: function () {
      console.log('_________')
      const app = this.$refs['appmaster']
      const blockSize = app.clientWidth / 2
      console.log('l ', app.offsetLeft)

      console.log(blockSize)
      const total = app.offsetLeft / 2
      console.log('total ', total)

      window.scrollTo(total, (app.offsetTop))
    }
  }
}
</script>

<style lang="scss" scoped>
.app {
    min-width: 200vw;
    min-height: 200vh;
}

.btn {
    margin: 0;
}

.btn-reset {
    position: fixed;
    top: 10px;
    left: 10px;
}

.app-master {
    box-shadow: 0 0 0 2px red;
}
</style>
