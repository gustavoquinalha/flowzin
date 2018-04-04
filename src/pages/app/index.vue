<template>
<<<<<<< HEAD
<div class="app container align-center text-align-center">

  <div class="app-content">

    <tree :text="father.text" :nodes="father.childrens" ref="role"/>

=======
<div class="">
  <button type="button" name="button" @click="resetPosition()" class="btn btn-reset">reset</button>

  <div class="app container align-center text-align-center" id="appc">
    <div class="app-master" ref="appmaster">
      <div class="app-content" ref="role">
        <tree :text="father.text" :nodes="father.childrens" /> </div>
    </div>
>>>>>>> d2aabb65eca1c6c5a63a89d08003f521eb493fae
  </div>

</div>
</template>

<script>
import Tree from '@/components/Tree'
export default {
  data () {
    return {
      father: {
<<<<<<< HEAD
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
=======
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
>>>>>>> d2aabb65eca1c6c5a63a89d08003f521eb493fae
      }
    }
  },
  components: {
    Tree
  },
  mounted () {
<<<<<<< HEAD
    const div = this.$refs['role'][0]
    console.log(div)

    window.scrollTo((div.offsetLeft / 2), (div.offsetTop - 100))
=======
    this.resetPosition()
  },
  methods: {
    resetPosition: function () {
      const app = this.$refs['appmaster']
      console.log(app.offsetLeft)
      // const tela = document.getElementsByClassName('app')
      // console.log(tela[0].clientWidth)

      window.scrollTo(app.offsetLeft / 2, (app.offsetTop))
    }
>>>>>>> d2aabb65eca1c6c5a63a89d08003f521eb493fae
  }
}
</script>

<style lang="scss" scoped>
.app {
    min-width: 200vw;
    min-height: 200vh;
<<<<<<< HEAD
    background: red;
    padding: 100px;
=======
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
    border: 2px solid yellow;
>>>>>>> d2aabb65eca1c6c5a63a89d08003f521eb493fae
}
</style>
