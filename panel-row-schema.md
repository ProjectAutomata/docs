### Panel Row Schema



```
{
    _id: Panel:ShortId,
    panelId: String,
    cells:[
        {
            panelPropId: String,
            values: Any
        }
    ],
    cellsObj:{
        panelPropId: {
            value: Any
        },
        ...
        ...
        ...
    }
}
```



