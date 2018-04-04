<template>
<div class="">
  <button type="button" name="button" @click="resetPosition()" class="btn btn-reset">reset</button>

  <div class="app container align-center text-align-center" id="appc">
    <div class="app-master" ref="appmaster">
      <div class="app-content" ref="role">
        <tree :text="father.text" :nodes="father.childrens" /> </div>
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
        childrens: [{
          text: 'Home'
        }, {
          text: 'Features',
          childrens: [{
            text: 'Features 1'
          }, {
            text: 'Features 2',
            childrens: [{
              text: 'Features 2 1'
            }, {
              text: 'Features 2 2'
            }]
          }]
        }, {
          text: 'Contact'
        }, {
          text: 'Products'
        }]
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
      const app = this.$refs['appmaster']
      const blockSize = app.clientWidth
      console.log(app.offsetLeft)

      console.log(blockSize)

      window.scrollTo(app.offsetLeft / 2, (app.offsetTop - 100))
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
