# Multiple Grid Structure:

### Model:

```
id: MongoId,
minHeight: n,
componentViewId: ObjectId,
position: Int,
columnStart: n<=16 && n!=-ve,
columnEnd: n<=16 && n!=-ve
```

# Grid Structure:

### Model:

```
id: MongoId,
label: String,
description: String,
multipleGridStructureId: ObjectId,
minHeight: n % gridHeight = 0
```

# Grid Block:

### Model:

```
id: MongoId,
gridStructureId: ObjectId,
position: Int,
minHeight: n % gridHeight = 0
```

# Grid Element:

### Model:

```
id: MongoId,
gridBlockId: ObjectId,
gridStructureId: ObjectId,
componentType: String,
panelPropId: ObjectId,
label: String,
description: String,
column: n<=16,
options:{
    readOnly: Boolean,
    showHelp: Boolean,
    showLabel: Boolean,
    showDescription: Boolean
},
componentOptions: {
    //tobeAdded..
}
```



