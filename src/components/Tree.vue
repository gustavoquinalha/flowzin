<template>
<ul class="role">
  <li>
    <div class="btn" :id="`box-${registerId}`">
      {{ text }}
      <div class="btn-drop container align-center text-align-center">
        <ul class="list-none">
          <li>
            <button type="button" name="button" class="btn btn-primary">Add</button>
          </li>
          <li>
            <button type="button" name="button" class="btn btn-danger">Remove</button>
          </li>
        </ul>
      </div>
    </div>
    <div class="container" :class="{ wrap : responsive}">
      <tree v-for="(node, index) in nodes" :nodes="node.childrens" :text="node.text" :key="`${node.text}${index}`" :id="'box-' + (index + 1)" :registerId="`${index}${text}`" />
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
    'registerId'
  ],
  data () {
    return {
      responsive: false
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
