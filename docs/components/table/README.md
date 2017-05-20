# Tables

> For tabular data. Tables support pagination and custom rendering.

### fields
Fields prop is used to display table columns.
keys are used to extract real value from each raw.
Example format:
```js
name: {
    label: 'Person Full name',
    sortable: true,
    invisible:true // Dynamically remove the field if needed from the table.
},
age: {
    label: 'Person age',
    sortable: false
}
```

### items
Items are real table data records. Example format:

```js
[
    {
        isActive: false,  // Adds special bootstrap styles
        state: 'success', // Displays record green
        age: 27,
        name: 'Havij'
    }
]
```

### Custom rendering
Custom rendering for each field is possible using **scoped slots**.
If you want to add an extra field which does not exits on records, just add it to `fields` object.  Example:

```js
// In your data object...
{
    fields: {
        name: {
            label: 'Person Full name',
            sortable: true
        },
    }
}
```

```html
<template slot="name" scope="item">
      {{item.value.first}} {{item.value.last}}
</template>
```

