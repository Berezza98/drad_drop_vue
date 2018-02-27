<template>
  <div id="app">
    <div class="draggable_wrapper">
      <div class="wrap">
          <draggable :parent="'body'" :return-to-start-position="true" :z="1" :drop-zone="'.drop'" @dropInside="droppedInside" @dragging="onDrag" @dragstop="drop">
            <div slot="main" class="img"></div>
          </draggable>
      </div>
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

    },
    droppedInside(){
      console.log('dropped inside');
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
    z-index: 0;
  }

  .img{
    height: 100%;
    width: 100%;
    outline: none;
    user-select: none;
    background: url('https://i.ytimg.com/vi/1yjlx2LRbYc/hqdefault.jpg');
  }

  .wrap{
    background: gold;
    height: 500px;
    width: 500px;
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
