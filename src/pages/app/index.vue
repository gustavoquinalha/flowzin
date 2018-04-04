<template>
<div class="app container align-center text-align-center" id="appc">
  <button type="button" name="button" @click="resetPosition()" class="btn btn-reset">reset</button>

  <div class="app-content" v-for="(node, index) in nodes" :key="`${node.text}${index}`" v-bind:ref="node.first?'role':''">

    <!-- <div ref="role"
         class="role">

      <div class="box border container column">

        <div class="btn btn-primary">
          Start
        </div>

        <div class="box2 border container column">

          <div class="container">
            <div class="btn btn-primary">
              Start
            </div>
            <div class="btn btn-primary">
              Start
            </div>
            <div class="btn btn-primary">
              Start
            </div>
          </div>

          <div class="box3 border container column">

            <div class="container">

              <div class="box-ref">
                <div class="btn btn-primary">
                  Start
                </div>
                <div class="btn btn-primary">
                  Start
                </div>
              </div>

              <div class="btn btn-primary">
                Start
              </div>
              <div class="btn btn-primary">
                Start
              </div>
            </div>
          </div>

        </div>

      </div>

      {{flow}}

    </div> -->

    <tree :text="node.text"
          :nodes="node.childrens" />

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
        childrens: [{
          text: 'Child'
        }, {
          text: 'Child1',
          childrens: [{
            text: 'Child12'
          }, {
            text: 'Child13',
            childrens: [{
              text: 'Child234'
            }, {
              text: 'Child245'
            }]
          }]
        }, {
          text: 'Child2'
        }, {
          text: 'Child3'
        }]
      }]
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
      const div = this.$refs['role']
      const widthBlock = div.clientWidth

      console.log('tamanho da div ', div.offsetLeft)
      console.log('tamanho da box azul: ', widthBlock)

      const total = div.offsetLeft - (widthBlock - 30) // 40 da borda - 10 do shadow

      console.log('total ', total)
      window.scrollTo(total, (div.offsetTop - 50))
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

.role {
    box-shadow: 0 0 0 5px blue;
    padding: 20px;
}

.btn-reset {
    position: fixed;
    top: 10px;
    left: 10px;
}

.border,
.box-ref {
    border: 1px solid red;
    padding: 10px;
}

.container {
    align-items: center;
    justify-content: center;
}
</style>
