The UI module adds some basic functionality that you can use in your directives to simplify animating and making responsive components.

``` typescript
import { ui } from ‘entcore’;

ui.extendElement.touchEvents(element);
ui.extendSelector.touchEvents(selector);
```

This allows the element or all elements matching the selector to listen to touch input. It will trigger some additional events:

`longclick`, `doubletap`, `swipe-right`, `swipe-left`, `swipe-up`, `swipe-bottom`

``` typescript
ui.extendElement.draggable(element, params);
ui.extendSelector.draggable(selector: string, params);
```

This makes the element or all elements matching the selector draggable. It will emit dragover and dragout on compatible elements (those having the droppable class). The params object contains various callbacks and options:

``` typescript
params: {
    // When the element is locked in a direction, it can only be moved in the   other direction
    lock?: { vertical: boolean, horizontal: boolea},

    // Callback called at every animation frame tick
    tick?: any,

    // Called when the element is dragged over a compatible element
    dragOver?: any,

    // Called when the element is dragged out of a compatible element
    dragOut?: any,

    // Called when the user starts dragging
    startDrag?: any,

    // Called on mouse up
    mouseUp?: any
}
```

> **Warning**
>
> It doesn’t work like the HTML5 drag and drop API, and therefore works with the touch input, and moves the element itself instead of duplicating it. If the element has a parent with the drawing-grid class, the element can’t be dragged outside the parent.

``` typescript
ui.extendElement.resizable(element);
ui.extendSelector.resizable(selector);
```

This makes the element or all elements matching the selector resizable. If it has a parent with the drawing-grid class, it can’t be resized outside the parent.

`ui.breakpoints`

The breakpoints matching those used in the CSS library.

`ui.scrollToTop()`

Scrolls the window to the top, with an animation.

`ui.scrollToId(id: string)`

Scrolls to the element with the matching id, = with an animation.
