### Problems

![](/assets/Automata Panel Row Design_1.jpg)![](/assets/Automata Panel Row Design_2.jpg)

### 

### Panel Row Schema

```
{
    _id: Panel:ShortId,
    panelId: String,
    cells:[
        {
            panelPropId: String,
            values: Any
        },
        {
            //related data case...
            panelPropId: String,
            value: Any,
            foreignRowId: String
        }
    ],
    cellsObj:{
        panelPropId: {
            value: Any
        },
        panelPropId:{
            value: Any,
            foreignRowId: String
        }
        ...
        ...
        ...
    }
}
```



