The selection tool is a basic utility to make working with lists of selectable items easier. It works by simply passing an array to a new Selection:

``` typescript
import { Selection } from ‘entcore-toolkit’;

const selection = new Selection(myArray);
```

The objects inside the Array should implement Selectable, which simply means they have a selected property. The selected property will be true when an user has selected the item, false otherwise.

The selection can then be used for various operations:


- Get all selected items : `selection.selected`
- Select all items : `selection.selectAll();`
- Deselect all items : `selection.deselectAll();`
- Number of selected items : `selection.length`
- Number of items in the whole collection : `selection.colLength`
- Select items matching predicate : `selection.select(e ⇒ e.name === ‘match’)`
- Remove selected items from the whole collection :  `selection.removeSelection()`


