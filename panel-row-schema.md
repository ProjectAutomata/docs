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

#### Examples

```
///Row 1
{
    _id: 1,
    cells:[
        {
            panelPropId: 'name',
            value: 'Robins'
        },
        {
            panelPropId: 'age',
            value: 18
        },
        {
            panelPropId: 'contactNumber',
            relatedData:[
                {
                    foreignRowId: 2,
                    value: '9953242338'
                }
            ]
        }
    ]

}
{
    _id: 2,
    cells:[
        {
            panelPropId: 'name',
            value: 'Ravi'
        },
        {
            panelPropId: 'age',
            value: 20
        },
        {
            panelPropId: 'contactNumber',
            relatedData:[
                {
                    foreignRowId: 3,
                    value: '9873046993'
                },
                {
                    foreignRowId: 3,
                    value: '9953242338'
                }
            ]
        }
    ]               
}
{
    _id: 3,
    cells:[
        {
            panelPropId: 'name',
            value: 'Rishi'
        },
        {
            panelPropId: 'age',
            value: 23
        },
        {
            panelPropId: 'contactNumber',
            relatedData:[
                {
                    foreignRowId: 3,
                    value: '9873046993'
                },
                {
                    foreignRowId: 3,
                    value: '9953242338'
                }
            ]
        }
    ]               
}
```





## Mongo Index

```

db.Test.createIndex({'cells.value':1, 'cells.relatedData.value':1})
db.Test.createIndex({'cells.relatedData.value':1})
db.Test.createIndex({'cells.value':1})

```





