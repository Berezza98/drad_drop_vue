# Vue.js  Vue-draggable-resizable changings

## Changes in Vue-draggable-resizable component:

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

2. Parent argument - selector of element(area where we can drag element). (String, optional, defaut = false)
```html
    <vue-draggable-resizable :parent="'.draggable_wrapper'"></vue-draggable-resizable>
```

3. New param `dropZone` - selector of element(area where we can drop element). (String, optional, defaut = false)
```html
    <vue-draggable-resizable :parent="'body'" :drop-zone="'.drop'"></vue-draggable-resizable>
```

4. CSS class `insideDropZone` will be added when droppable element is situated abowe `drop-zone`

5. Added new papam `returnToStartPosition`(Boolean, optional, defaut = false) for set initial position of element after drop element
```html
    <vue-draggable-resizable :parent="'body'" :drop-zone="'.drop'" :returnToStartPosition="true"></vue-draggable-resizable>
```

6. Added new param `setParentSizes` for setting sizes of parent block for draggable element. (Boolean, optional, defaut = false)
```html
    <vue-draggable-resizable :parent="'body'" :setParentSizes="true" :drop-zone="'.drop'" :returnToStartPosition="true"></vue-draggable-resizable>
```

7. New event `dropInside` emits when dragging element have dropped inside `dropZone`


