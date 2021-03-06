## PANEL PROPERTIES

| Type | Features |
| :--- | :--- |
| Link to another panel | Single, Multiple, Select Panel, Choose Fields |
| Single Line Text |  |
| Long Text |  |
| Attachment |  |
| Checkbox |  |
| Multiple Select | With Color Select and Option to add Options |
| Single Select | With Color Select and Options to add Options |
| Subscriber | Event Select //DISCUSS STORAGE MEDIUM. |
| Date | Indian, Friendly, US Standard, European, ISO, Store in backend in format of ISO date |
| Time | 12 Hour,  24 Hour, store in form of seconds of 12 hour o 24 hour format. |
| Duration | hh:mm:ss Check Airtable, Zoho Sprint. At backend its value will get stored in form of number in seconds. |
| Phone number | Just formatted design like AirBnb |
| Email |  |
| Url |  |
| Number | Select Integer or Decimal\(1.0\) + Precision |
| Currency | Currency Symbol + Precision + Allow -ve number |
| Percent | Precision + Allow -ve number |
| Rating | Max number \(Select out of 10\) |
| Created Date | \(Ask for Options Also Display Time\) |
| Updated Date | \(Ask for option to also display time\) |

| **Single Line Text** |
| :--- |
| Default |
| Min Length |
| Is Required |
| Suffix |
| Prefix |
| Regex |
| Is Primary |

| Long Text |
| :--- |
| Default |
| Min Length |
| Max Length |
| Is Required |
| Suffix |
| Prefix |
| Regex |
| Is Primary |

| Attachment |
| :--- |
| Is Required |

| Checkbox |
| :--- |
| Default |
| Is Required |

| Multiple Select |
| :--- |
| Is Required |

| Single Select |
| :--- |
| Default |
| Is Required |

| Subscriber |
| :--- |
| Is Required |
| Select Event |

| Date |
| :--- |
| Is Required |
| Indian, friendly, US standard, European |

| Time |
| :--- |
| Is Required |

| Phone number |
| :--- |
| Is Required |
| is Primary |

| Currency |
| :--- |
| isRequired |
| Default |

| Percent |
| :--- |
| is Required |
| Default |

| Created Date |
| :--- |
| Indian, friendly, US standard, European |

| Updated Date |
| :--- |
| Indian, friendly, US standard, European |

| Email |
| :--- |
| Is Required |
| is Primary |

| URL |
| :--- |
| Is Required |
| Is Primary |

| Rating |
| :--- |
| Is Required |
| Is Primary |

| Number |
| :--- |
| Default |
| Is Primary |
| Regex |
| Min |
| Max |
| Is Required |
| GTE, LTE |
| Suffix |
| Prefix |

| Link to Another Panel |
| :--- |
| Single, Multiple |
| Select Panel |
| Select Search Field |
| Select Display Fields |
| Is Required |

### Single Line Text

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
        name: 'String'
        type: 'singleLineText',
        typeOptions:{
            default: 'String',
            minLength: 'Number',
            isRequired: 'Boolean',
            suffix:'String',
            prefix: 'String',
            regex: 'String' //Must be a valid RegExp
            isPrimary: 'Boolean'
        },
        panelId: 'PanelID REFERENCE'
    }
}
```

### Long Text

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
        name: 'String'
        type: 'longText',
        typeOptions:{
            default: 'String',
            minLength: 'Number',
            maxLength: 'Number',
            isRequired: 'Boolean',
            suffix:'String',
            prefix: 'String',
            regex: 'String' //Must be a valid RegExp
            isPrimary: 'Boolean'
        },
        panelId: 'PanelID REFERENCE'
    }
}
```

### Attachment

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
            name: 'String'
            type: 'attachment',
            typeOptions:{
                isRequired: 'Boolean'
        },
        panelId: 'PanelID REFERENCE'
    }
}
```

### Checkbox

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
            name: 'String'
            type: 'checkbox',
            typeOptions:{
                isRequired: 'Boolean',
                default: 'Boolean'
        },
        panelId: 'PanelID REFERENCE'
    }
}
```

### Multiple Select

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
            name: 'String'
            type: 'multipleSelect',
            typeOptions:{
                isRequired: 'Boolean',
                options: [
                    {
                        value: 'String',
                        color: '#aabbcc'
                    }
                ]
        },
        panelId: 'PanelID REFERENCE'
    }
}
```

### Single Select

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
            name: 'String'
            type: 'singleSelect',
            typeOptions:{
                isRequired: 'Boolean',
                options: [
                    {
                        value: 'String',
                        color: '#aabbcc'
                    }
                ]
                default
        },
        panelId: 'PanelID REFERENCE'
    }
}
```

### Subscriber //Always will be a multiple select

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
            name: 'String'
            type: 'subscriber',
            typeOptions:{
                isRequired: 'Boolean',
                eventId: 'EVENT MODEL REFERENCE'
        },
        panelId: 'PanelID REFERENCE'
    }
}
```

### Date

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
            name: 'String'
            type: 'date',
            typeOptions:{
                isRequired: 'Boolean',
                formatType: 'MM-DD-YYYY' //Check moment.js docs
        },
        panelId: 'PanelID REFERENCE'
    }
}
```

### Phone Number

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
            name: 'String'
            type: 'phoneNumber',
            typeOptions:{
                isRequired: 'Boolean',
                isPrimary: 'Boolean'
        },
        panelId: 'PanelID REFERENCE'
    }
}
```

### Currency

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
            name: 'String'
            type: 'currency',
            typeOptions:{
                isRequired: 'Boolean',
                precision: 'Number' 1-10 1.0 -> 1.0^10
                default: '',
                allowNegative: 'Boolean',
                symbol: '$'
        },
        panelId: 'PanelID REFERENCE'
    }
}
```

### Percent

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
            name: 'String'
            type: 'percent',
            typeOptions:{
                isRequired: 'Boolean',
                precision: 'DECIMAL' 1.0 -> 1.0^10,
                allowNegative: 'Boolean'
                default: ''
        },
        panelId: 'PanelID REFERENCE'
    }
}
```

### Created Date

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
        name: 'String'
        type: 'createdDate',
        typeOptions:{
            showTime: 'Boolean',
            timeFormat: '12hour|24hour' //if showTime === true
        },
        panelId: 'PanelID REFERENCE'
    }
}
```

### Updated Date

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
        name: 'String'
        type: 'updatedDate',
        typeOptions:{
            showTime: 'Boolean',
            timeFormat: '12hour|24hour' //if showTime === true
        },
        panelId: 'PanelID REFERENCE'
    }
}
```

### Time

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
            name: 'String'
            type: 'time',
            typeOptions:{
                isRequired: 'Boolean',
                timeFormat: '12hour|24hour'
        },
        panelId: 'PanelID REFERENCE'
    }
}
```

### Email

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
            name: 'String'
            type: 'email',
            typeOptions:{
                isRequired: 'Boolean',
                isPrimary: 'Boolean'
        },
        panelId: 'PanelID REFERENCE'
    }
}
```

### Url

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
            name: 'String'
            type: 'url',
            typeOptions:{
                isRequired: 'Boolean',
                isPrimary: 'Boolean'
        },
        panelId: 'PanelID REFERENCE'
    }
}
```

### Rating

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
            name: 'String'
            type: 'rating',
            typeOptions:{
                isRequired: 'Boolean',
                default: '',
                max: '' 1-10 number
        },
        panelId: 'PanelID REFERENCE'
    }
```

### Number

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
            name: 'String'
            type: 'number',
            typeOptions:{
                isRequired: 'Boolean',
                default: '',
                min: 'Number',
                max: 'Number',
                gte: 'Number',
                lte: 'Number',
                suffix: 'Any',
                prefix: 'Any',
                isPrimary: 'Boolean',
                regex: 'REGEXP String',
                numberType: 'decimal|integer' //Default: Integer,
                allowNegative: false,
                precision: 'Number', 1-10 1 means 1.0, 2 means 1.00  //if numberType === 'decimail'
        },
        panelId: 'PanelID REFERENCE'
    }
}
```

### LinkToAnotherPanel

```
{
    _id: 'projectId:panelShortId:shortId',
    payload: {
            name: 'String'
            type: 'linkToAnotherPanel',
            typeOptions:{
                isRequired: 'Boolean',
                relatedPanelId: '',
                relatedPanelPropId: '',
                type: 'Single|Multiple',
                displayFields:[
                  {
                    name: 'ABC',
                    panelPropId: ''
                  }   
                ]
        },
        panelId: 'PanelID REFERENCE'
    }
}
```



