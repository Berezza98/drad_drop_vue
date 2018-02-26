<template>
  <div id="app">
    <div class="draggable_wrapper">
      <draggable :parent="'body'" class="bor" :drop-zone="'.drop'" @dragging="onDrag" @dragstop="drop">
      </draggable>
    </div>
    <div class="drop">

    </div>
  </div>
</template>

<script>
import VueDraggableResizable from './components/vue-draggable-resizable.vue'

export default {
  name: 'app',
  components: {
    'draggable': VueDraggableResizable
  },
  data () {
    return {
      canDrop: false
    }
  },
  methods: {
    onDrag(x, y, event){

    },
    drop(x, y){

    }
  }
}
</script>

<style>
  .roman{
    border:2px solid red !important;
  }
  .drop{
    height: 600px;
    width: 600px;
    background: paleturquoise;
  }

  .element{
    width: 100%;
    height: 100%;
  }

  .draggable_wrapper{
    height: 800px;
    width: 800px;
    background: lightcoral;
  }

  .insideDropZone{
    border: 2px solid green;
  }

  .bor{
    background: indigo;
  }
</style>
