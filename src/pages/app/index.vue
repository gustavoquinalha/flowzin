<template>
<div class="app container align-center text-align-center">

  <div class="app--content">

    <div ref="role" class="role">
       <div class="btn">
         Start
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
    // window.location.hash = '#role'
    const div = this.$refs['role']
    const tela = window

    console.log('innerWidth:', tela.innerWidth)
    console.log('innerHeight:', tela.innerHeight)

    console.log(div.offsetLeft)
    console.log(div.offsetRight)
    console.log(div.offsetTop)
    console.log(div.offsetBottom)

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

.role {
  border: 5px solid blue;
}
</style>
