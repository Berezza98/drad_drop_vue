# Vue.js  Vue-draggable-resizable changings

## Changes in Vue-draggable-resizable module:

1. Dragging handler can accept one more argument - event
```
    onDrag(x, y, event){
      if(this.isInside(event.clientX, event.clientY, '.drop')){
        this.canDrop = true;
      }else{
        this.canDrop = false; 
      }
    }
```
2. parent argument - selector of element(area where we can drag element) String
```
    <vue-draggable-resizable :parent="'.draggable_wrapper'"></vue-draggable-resizable>
```


