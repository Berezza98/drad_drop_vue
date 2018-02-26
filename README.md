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
2. Parent argument - selector of element(area where we can drag element) String
```html
    <vue-draggable-resizable :parent="'.draggable_wrapper'"></vue-draggable-resizable>
```
3. New param dropZone - selector of element(area where we can drop element) String
```html
    <vue-draggable-resizable :parent="'body'" :drop-zone="'.drop'"></vue-draggable-resizable>
```
4. CSS class `insideDropZone` will be added when droppable element is situated abowe `drop-zone`
5. Added `initialPosition` property inside component
6. Added new papam `returnToStartPosition`(Boolean, optional, defaut = false) for set initial position of element after drop element
```html
    <vue-draggable-resizable :parent="'body'" :drop-zone="'.drop'" :returnToStartPosition="true"></vue-draggable-resizable>
```
7. Added property `clone`(Boolean, optional, defaut = false) for clonning dragging element into the `drop-zone`
```html
    <vue-draggable-resizable :clone="true" :parent="'body'" :drop-zone="'.drop'" :returnToStartPosition="true"></vue-draggable-resizable>
```
8. Added two types of slots: `main` - for main content and `clone` for content that will be cloned into the `drop-zone` if property `clone = true`
```html
     <draggable :parent="'body'" :clone="true" :return-to-start-position="true" :drop-zone="'.drop'" @dragging="onDrag" @dragstop="drop">
      <div slot="main">main content</div>
      <div slot="clone">content for clonning</div>
    </draggable>
```

