# Vue.js  Vue-draggable-resizable changings

## Changes in Vue-draggable-resizable module:

1. Dragging handler can accept one more argument - event
```javascript
    onDrag(x, y, event){
      if(this.isInside(event.clientX, event.clientY, '.drop')){
        this.canDrop = true;
      }else{
        this.canDrop = false; 
      }
    }
```
2. Parent argument - selector of element(area where we can drag element) String
```html
    <vue-draggable-resizable :parent="'.draggable_wrapper'"></vue-draggable-resizable>
```
3. New param dropZone - selector of element(area where we can drop element) String
```html
    <vue-draggable-resizable :parent="'body'" :drop-zone="'.drop'"></vue-draggable-resizable>
```
4. CSS class `insideDropZone` will be added when droppable element is situated abowe `drop-zone` 


