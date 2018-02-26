<template>
  <div id="app">
    <draggable @dragging="onDrag" @dragstop="drop">
      <div :class="{'roman': canDrop}"></div>
    </draggable>
    <div class="drop">

    </div>
  </div>
</template>

<script>
import VueDraggableResizable from 'vue-draggable-resizable'

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
    onDrag(x, y){
      if(this.isInside(x, y)){
        this.canDrop = true;
      }else{
        this.canDrop = false; 
      }
    },
    drop(x, y){
      console.log(x, y);
    },
    isInside(x, y){
      let dropElem = document.querySelector('.drop');
      let dropWidth = dropElem.offsetWidth;
      let dropHeight = dropElem.offsetHeight;
      let {left, top} = dropElem.getBoundingClientRect();
      if(y < top + dropHeight && y > top && x < left + dropWidth && x > left){
          return true;
      }else{
        return false;
      }
    }
  }
}
</script>

<style>
  .roman{
    width: 100%;
    height: 100%;
    background: red;
  }
  .drop{
    height: 600px;
    width: 600px;
    background: paleturquoise;
  }
</style>
