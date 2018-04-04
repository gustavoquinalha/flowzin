<template>
<div class="">

  <div class="app container text-align-center" id="appc">
    <div class="app-master" ref="appmaster">
      <div class="app-content" ref="role">
        <tree :text="father.text" :nodes="father.childrens" ref="role" />
      </div>
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
            text: 'Feature 1'
          }, {
            text: 'Feature 2',
            childrens: [{
              text: 'Feature 2 1'
            }, {
              text: 'Feature 2 2'
            }]
          }]
        }, {
          text: 'Mapa'
        }, {
          text: 'Contato'
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
      // console.log('_________')
      // const app = this.$refs['appmaster']
      // console.log('app left ', app.offsetLeft)
      // const blockSize = app.clientWidth
      // console.log(blockSize)
      //
      // const total = app.offsetLeft / 2
      //
      // window.scrollTo(total, (app.offsetTop))
    }
  }
}
</script>

<style lang="scss" scoped>
.app {
    width: 100vw;
    height: 100vh;
    overflow: auto;
    box-sizing: border-box;
    // background: red;
}

.btn {
    margin: 0;
}

.btn-reset {
    position: fixed;
    top: 10px;
    left: 10px;
    box-shadow: 0 0 30px 0 rgba(0, 0, 0, .5);
    padding: 0;
    width: 60px;
    height: 60px;
    border-radius: 50%;
}

.app-master {
    padding: 10vw;
    box-shadow: 0 0 0 2px red;
    margin: 0 auto;
}
</style>
