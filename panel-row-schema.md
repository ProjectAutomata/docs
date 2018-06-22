
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
    cellObj:{
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
    cells\Obj:{
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

#### Single Line Text

```
{
    _id: 3,
    payload:{
    cells:[
        {
            panelPropId: 'name',
            value:"Robins Kumar Gupta"
        }
    ]               
}
```

#### Long Text

```
{
    _id: 3,
    payload:{
    cells:[
        {
            panelPropId: 'name',
            value:"This is a long Text example."
        }
    ]               
}
```

#### Attachment

```
{
  _id: 3,
  payload:{
    cells:[
       {
           panelPropId: 'documents',
           value:[
               {
                  snaphyImageId: '',
                  container:'',
                  name: '',
                  mime: ''
               }
           ]
        }
      ]
   } 
}
```

## Checkbox

```
{
    _id: 3,
   payload:{
     cells:[
       {
           panelPropId: 'isChecked',
           value: true|false
        }
      ]
   } 
}
```

#### Multiple Select

```
{
    _id: 3,
   payload:{
     cells:[
       {
           panelPropId: 'fruits',
           value: ['apple', 'banana']
        }
      ]
   } 
}
```

#### Single Select

```
{
    _id: 3,
   payload:{
     cells:[
       {
           panelPropId: 'status',
           value: 'active'
        }
      ]
   } 
}
```

#### Subscriber

```
{
    _id: 3,
   payload:{
     cells:[
       {
           panelPropId: 'subscriber',
           value: 'active'
        }
      ]
   } 
}
```

#### Date

```
{
   _id: 3,
   payload:{
     cells:[
       {
           panelPropId: 'date',
           value: 'Thu Jun 21 2018 17:58:37 GMT+0530'
        }
      ]
   } 
}
```

#### Time

```
{
   _id: 3,
   payload:{
     cells:[
       {
           panelPropId: 'date',
           value: '1230123' //In seconds
        }
      ]
   } 
}
```

#### Duration

```
{
   _id: 3,
   payload:{
     cells:[
       {
           panelPropId: 'duration',
           value: '120' //In seconds
        }
      ]
   } 

}
```

## Phone Number

```
{
    _id: 3,
    payload:{
         cells:[
              {
                   panelPropId: 'phoneNumber',
                   value: '9953242338'
              }
         ]   
    }
}
```

## Email

```
{
   _id: 3,
   payload:{
      cells:[
         {
             panelPropId: 'email',
             value: 'robins@snaphy.com'
         }
      ]
   }
}
```

## Url

```
{
   _id: 3,
   payload:{
      cells:[
         {
             panelPropId: 'url',
             value: 'http://www.google.com'
         }
      ]
   }
}
```

#### Number

```
{
    _id: 3,
    payload:{
        cells:[
            {
                panelPropId: 'number',
                value: 23
            }
        ]
    }
}
```

#### Currency

```
{
    _id: 3,
    payload:{
        cells:[
            {
                panelPropId: 'currency',
                value: 1234
            }
        ]
    }
}
```

#### Percent

```
{
    _id: 3,
    payload:{
        cells:[
            {
                panelPropId: 'percent',
                value: 60
            }
        ]
    }
}
```

#### Rating

```
{
    _id: 3,
    payload:{
        cells:[
            {
                panelPropId: 'rating',
                value: 50
            }
        ]
    }
}
```

#### Created Date \| Updated Date

```
{
    _id: 3,
    payload: {
        cells:[
            {
                panelPropId: 'createdDate|updatedDate',
                value: 'ISO DATE'
            }
        ]
    }
}
```

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
db.Test.createIndex({'cells':1})
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

