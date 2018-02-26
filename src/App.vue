<template>
  <div id="app">
    <div class="draggable_wrapper">
      <draggable :parent="'.draggable_wrapper'" @dragging="onDrag" @dragstop="drop">
        <div :class="{'roman': canDrop, 'element': true}">
        </div>
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
      if(this.isInside(event.clientX, event.clientY, '.drop')){
        this.canDrop = true;
      }else{
        this.canDrop = false; 
      }
    },
    drop(x, y){
      console.log(x, y);
    },
    isInside(x, y, selector){
      let dropElem = document.querySelector(selector);
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
    border: 2px solid green;
  }

  .draggable_wrapper{
    height: 800px;
    width: 800px;
    background: lightcoral;
  }
</style>
