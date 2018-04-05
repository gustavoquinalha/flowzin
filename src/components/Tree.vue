<template>
<ul class="role">
  <li>
    <div class="btn" :id="`box-${registerId.replace(' ', '')}`">
      {{ text }}
      <div class="btn-drop container align-center text-align-center">
        <ul class="list-none">
          <li>
            <button type="button" name="button" class="btn btn-primary" @click="addChild()">Add</button>
          </li>
          <li>
            <button type="button" name="button" class="btn btn-purple" @click="editText(index)">Edit</button>
          </li>
          <li v-if="index || index >= 0">
            <button type="button" name="button" class="btn btn-danger" @click="removeNode(index)">Remove</button>
          </li>
        </ul>
      </div>
    </div>
    <div class="container" :class="{ wrap : responsive}">
      <tree v-for="(node, index) in nodes" :nodes="node.childrens" :text="node.text" :key="`${node.text}${index}`" :id="'box-' + (index + 1)" :registerId="`${index}${text}`" :element="nodes" :index="index"/>
    </div>
  </li>
</ul>
</template>

<script>
export default {
  name: 'tree',
  props: [
    'nodes',
    'text',
    'registerId',
    'element',
    'index'
  ],
  data () {
    return {
      responsive: false
    }
  },
  methods: {
    addChild () {
      console.log(this.nodes)
      const text = prompt('Informe o texto: ')
      this.nodes.push({ text: text, childrens: [] })
    },
    removeNode (index) {
      console.log(index)
      this.element.splice(index, 1)
      console.log(this.element)
    },
    editText (index) {
      const text = prompt('Informe o novo texto: ')
      if (index >= 0) this.element[index].text = text
      else this.element.text = text
    }
  }
}
</script>

<style lang="scss" scoped>
.btn {

    .btn-drop {
        display: none;
        background: $color-white;
        border-radius: $radius;
        width: 150px;
        min-height: 60px;
        position: absolute;
        left: calc(50% + 50px);
        top: 5px;
        z-index: 100;
        box-shadow: 0 0 5px 0 rgba(0,0,0,.3);
        justify-content: center;
        align-items: center;
        padding: 10px;
        box-sizing: border-box;
        ul {
            li {
                .btn {
                    width: 100%;
                }
                margin-bottom: 10px;
                &:last-child {
                    margin-bottom: 0;
                }
            }
        }
    }
    &:hover {
        .btn-drop {
            display: flex;
        }
    }
}

.app-master {
    .role {
        box-shadow: 0 0 0 1px blue;
        position: relative;
        margin: 5px;
        padding: 5px;
        box-sizing: border-box;
        li {
            .container {
                .btn {}
            }
        }
    }
}

#box-father {
    background: $color-primary;
    color: #fff;
}

.btn-drop {}
</style>
