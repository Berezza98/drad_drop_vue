<template>
  <div id="app">
    <div class="draggable_wrapper">
      <draggable :parent="'body'" :clone="true" :return-to-start-position="true" :drop-zone="'.drop'" @dragging="onDrag" @dragstop="drop">
        <div slot="main" class="img"></div>
        <draggable slot="clone" :parent="'.drop'" :drop-zone="'.drop'" @dragging="onDrag" @dragstop="drop">
          <div slot="main" class="img"></div>
        </draggable>
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
    overflow: hidden;
    position: relative;
  }

  .img{
    height: 100%;
    width: 100%;
    outline: none;
    user-select: none;
    background: url('https://i.ytimg.com/vi/1yjlx2LRbYc/hqdefault.jpg');
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
