<template>
<div class="app container align-center text-align-center"
     id="appc"
     style="position: relative">
  <button type="button" name="button" @click="resetPosition()" class="btn btn-reset">reset</button>

  <div class="app--content">

    <div ref="role" class="role">

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

    </div>

  </div>

</div>
</template>

<script>
export default {
  data () {
    return {

    }
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
