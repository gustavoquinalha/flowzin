<template>
<div class="app container align-center text-align-center">

  <div class="app--content">

    <div class="btn"
         id="role"
         ref="role">
      Start
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
    console.log(div.offsetLeft)
    console.log(div.offsetRight)
    console.log(div.offsetTop)
    console.log(div.offsetBottom)

    // this.$refs['role'].focus()
    // console.log(this.$refs['role'])
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
