
---

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
            panelPropId: 'Local Panel Prop ID',
            relatedData:[
                {
                    foreignRowId: "Related Panel Row Id",
                    value: '9953242338'
                }
            ]
        },
    ],
    cellsObj:{
        panelPropId: {
            value: Any
        },
        panelPropId:{
            relatedData:[
                {
                    foreignRowId: "Related Panel Row Id",
                    value: '9953242338'
                }
            ]

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
    ],
    cellsObj:{
        name: {
            value: 'Robins'
        },
        age: {
            value: 18
        },
        contactNumber: {
            relatedData:[
                {
                    foreignRowId: 2,
                    value: '9953242338'
                }
            ]
        },

    }

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

### Panel Row Data Conversion and Storage

| Properties | Features | Storage Mechanism |
| :--- | :--- | :--- |
| Link to another panel | Single, Multiple, Select Panel, Choose Fields |  |
| Single Line Text |  |  |
| Long Text |  |  |
| Attachment |  |  |
| Checkbox |  |  |
| Multiple Select | With Color Select and Option to add Options |  |
| Single Select | With Color Select and Options to add Options |  |
| Subscriber | Event Select //DISCUSS STORAGE MEDIUM. |  |
| Date | Indian, Friendly, US Standard, European, ISO, Store in backend in format of ISO date |  |
| Time | 12 Hour,  24 Hour, store in form of seconds of 12 hour o 24 hour format. |  |
| Duration | hh:mm:ss Check Airtable, Zoho Sprint. At backend its value will get stored in form of number in seconds. |  |
| Phone number | Just formatted design like AirBnb |  |
| Email |  |  |
| Url |  |  |
| Number | Select Integer or Decimal\(1.0\) + Precision |  |
| Currency | Currency Symbol + Precision + Allow -ve number |  |
| Percent | Precision + Allow -ve number |  |
| Rating | Max number \(Select out of 10\) |  |
| Created Date | \(Ask for Options Also Display Time\) |  |
| Updated Date | \(Ask for option to also display time\) |  |

#### Link to another panel \[Single\|Multiple\]

```
{
    _id: 3,
    cells:[
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

## 

## 

## 

## Sample Query

```
db.Test.find({ 
    $and:[
        {
            'cells.panelPropId':'age', 
            'cells.value': {
                $lt: 21
            }
        },
        {
            'cells.panelPropId':'contactNumber', 
            'cells.relatedData.value': '9873046993' 
        },
        {
            $or:[
                {
                    'cells.panelPropId':'name', 
                    'cells.value': 'Robins'
                },
                {
                    'cells.panelPropId':'age', 
                    'cells.value': {
                        $gt: 18
                    }
                }
            ]
        }
    ]   
})
```

## 

## Mongo Index

```
db.Test.createIndex({'cells.value':1, 'cells.relatedData.value':1})
db.Test.createIndex({'cells.relatedData.value':1})
db.Test.createIndex({'cells.panelPropId':1, 'cells.value':1})
db.Test.createIndex({'cells.panelPropId':1})
db.Test.createIndex({'cells.panelPropId':1, 'cells.value':1, 'cells.relatedData.value':1})
db.Test.createIndex({ 'cells.panelPropId':1, 'cells.relatedData.foreignRowId':1 })
```

### How related document will get update?

When updating a PanelRow document. Find all the panelProp of the current in edit document.  
Prepare a list of PanelPropId of current PaneRow Document.

For each PanelPropId Check in Panel Row Which has been modified.

[http://mongoosejs.com/docs/api.html\#document\_Document-isModified](/Mongoose Check If Properties has been modified or not)

If Modified:

```
Add Following To Promise List and Run **Promise** all method
```

* Find a search in PanelProp checking where it has been referenced as `relatedPanelPropId`.
* Get list of all the related properties and its PanelPropId.
  * For Each PanelPropId
  * Now run a Update Query to update data whose   **\`cells.relatedData.foreignRowId\` === 'CurrentInEditRowId' && cells.PanelPropId ===  PanelPropId**
  * update both cells and celObj values.           

#### 

#### What will happen when a PanelProp will get removed ?

On removing a PanelProp run a update query to remove all the cells containing PanelProp. Also remove all the Cells where this panelProp is refrenced as foreignKey.

