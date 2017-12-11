### Panel Grid View

![](/assets/AutomataWork.svg)

#### Tasks List \(Work Need To Be Done\)

* [ ] Design grid view
* [ ] Design view fetching methods and graphql
* [ ] Integrate view with dynamic data.
* [ ] Integrate view with filter and sort.

* [ ] Integrate card design with data

* [ ] Implement load more

* [ ] implement loading bar & error pages.

* [ ] Screen to add new data to calendar view

* [ ] Setting and Edit View Screen

#### Total Time

| Features | Screens | Design Time | Logic Time | Priority |
| :--- | :--- | :--- | :--- | :--- |
| Design grid view | 1 | 16 |  |  |
| Design view fetching methods and graphql |  |  | 10 |  |
| Integrate view with filter and sort |  |  | 4 |  |
| Design Row for calendar view | 1 | 6 |  |  |
| Implement load more |  |  | 2 |  |
| Implement loading bar and error pages | 1 | 2 | 1 |  |
| Screen to add new data to  view | 1 | 6 | 4 |  |
| Setting and Edit View Screen | 1 |  | 2 |  |

#### Screens

| Screen | Comment | Merge Status |
| :--- | :--- | :--- |
| grid\_view\_screen |  |  |
| grid\_view\_cards |  |  |
| grid\_view\_dialogs |  |  |
| grid\_view\_error\_pages |  |  |
| grid\_view\_new\_data |  |  |
| grid\_view\_setting |  |  |

#### Possible PanelProps for Adding Data

##### Primary Info

* Customer Name
* Title

##### Address

* Street
* City
* State
* Zip Code
* Country

##### Other

* Description
* Note

##### Contact

* Website
* Email
* Skype
* Phone Number

##### Company

* Company Name
* Industry
* Annual Revenue

##### Lead

* Status
* Owner

#### Architectural Design

![](/assets/New Doc 2017-12-09_1.jpg)

#### Basic Components

1. Single Line Text
2. Multi Line Text
3. Single Select
4. Multi Select
5. Single Related
6. Number
7. Date
8. Time
9. Boolean
10. Single File Upload
11. Multiple File Upload

#### Single Line Text

```
Options:{
    Dimension:{
        Width: n <= 16,
        Height: n * Grid
    },
    Label: String,
    Description: String,
    helpText: String,
    readOnly: Boolean,
    isDisabled: Boolean (default: false)
    showLabel: Boolean (default: true),
    showDescription: Boolean (default: true)
    showHelp: Boolean,
    typeOptions: {
        type: default|Email|Phone Number|Credit Card|Currency
    },
    readOnlyOptions: {
        textAlign: center|left|right,
        fontSize: xs|sm|md|lg|xl,
        fontWeight: normal|bold|bolder,
        color: "#--"
    }
    panelPropId: ID
}
```

#### Multi Line Text

```
Options:{
    Dimension:{
        Width: n <= 16,
        Height: n * Grid
    },
    Label: String,
    Description: String,
    helpText: String,
    readOnly: Boolean,
    isDisabled: Boolean (default: false)
    showLabel: Boolean (default: true),
    showDescription: Boolean (default: true)
    showHelp: Boolean,
    readOnlyOptions: {
        textAlign: center|left|right,
        fontSize: xs|sm|md|lg|xl,
        fontWeight: normal|bold|bolder,
        color: "#--"
    }
    panelPropId: ID
}
```

#### Single Select

```
Options:{
    Dimension:{
        Width: n <= 16,
        Height: n * Grid
    },
    Label: String,
    Description: String,
    helpText: String,
    readOnly: Boolean,
    isDisabled: Boolean (default: false)
    showLabel: Boolean (default: true),
    showDescription: Boolean (default: true)
    showHelp: Boolean,
    typeOptions: {
        type: default|City|State|Country
    },
    readOnlyOptions: {
        textAlign: center|left|right,
        fontSize: xs|sm|md|lg|xl,
        fontWeight: normal|bold|bolder,
        color: "#--"
    }
    panelPropId: ID
}
```

#### Multi Select

```
Options:{
    Dimension:{
        Width: n <= 16,
        Height: n * Grid
    },
    Label: String,
    Description: String,
    helpText: String,
    readOnly: Boolean,
    isDisabled: Boolean (default: false)
    showLabel: Boolean (default: true),
    showDescription: Boolean (default: true)
    showHelp: Boolean,
    readOnlyOptions: {
        textAlign: center|left|right,
        fontSize: xs|sm|md|lg|xl,
        fontWeight: normal|bold|bolder,
        color: "#--"
    }
    panelPropId: ID
}
```

#### Single Related

```
Options:{
    Dimension:{
        Width: n <= 16,
        Height: n * Grid
    },
    Label: String,
    Description: String,
    helpText: String,
    readOnly: Boolean,
    isDisabled: Boolean (default: false)
    showLabel: Boolean (default: true),
    showDescription: Boolean (default: true)
    showHelp: Boolean,
    typeOptions: {
        subtitles:[
            label: String,
            panelPropId: ID
        ]
    },
    readOnlyOptions: {
        textAlign: center|left|right,
        fontSize: xs|sm|md|lg|xl,
        fontWeight: normal|bold|bolder,
        color: "#--"
    }
    panelPropId: ID
}
```

#### Number

```
Options:{
    Dimension:{
        Width: n <= 16,
        Height: n * Grid
    },
    Label: String,
    Description: String,
    helpText: String,
    readOnly: Boolean,
    isDisabled: Boolean (default: false)
    showLabel: Boolean (default: true),
    showDescription: Boolean (default: true)
    showHelp: Boolean,
    typeOptions: {
        type: default|Age|ZipCode|Year
    },
    readOnlyOptions: {
        textAlign: center|left|right,
        fontSize: xs|sm|md|lg|xl,
        fontWeight: normal|bold|bolder,
        color: "#--"
    }
    panelPropId: ID
}
```

#### Date

```
Options:{
    Dimension:{
        Width: n <= 16,
        Height: n * Grid
    },
    Label: String,
    Description: String,
    helpText: String,
    readOnly: Boolean,
    isDisabled: Boolean (default: false)
    showLabel: Boolean (default: true),
    showDescription: Boolean (default: true)
    showHelp: Boolean,
    typeOptions: {
        type: Created (date)
    },
    readOnlyOptions: {
        textAlign: center|left|right,
        fontSize: xs|sm|md|lg|xl,
        fontWeight: normal|bold|bolder,
        color: "#--"
    }
    panelPropId: ID
}
```

#### Time

```
Options:{
    Dimension:{
        Width: n <= 16,
        Height: n * Grid
    },
    Label: String,
    Description: String,
    helpText: String,
    readOnly: Boolean,
    isDisabled: Boolean (default: false)
    showLabel: Boolean (default: true),
    showDescription: Boolean (default: true)
    showHelp: Boolean,
    readOnlyOptions: {
        textAlign: center|left|right,
        fontSize: xs|sm|md|lg|xl,
        fontWeight: normal|bold|bolder,
        color: "#--"
    }
    panelPropId: ID
}
```

#### File Upload

```
Options:{
    Dimension:{
        Width: n <= 16,
        Height: n * Grid
    },
    Label: String,
    Description: String,
    helpText: String,
    readOnly: Boolean,
    isDisabled: Boolean (default: false)
    showLabel: Boolean (default: true),
    showDescription: Boolean (default: true)
    showHelp: Boolean,
    typeOptions: {
        type: file|audio|img|video
    },
    readOnlyOptions: {
        textAlign: center|left|right,
        fontSize: xs|sm|md|lg|xl,
        fontWeight: normal|bold|bolder,
        color: "#--"
    }
    panelPropId: ID
}
```

#### Work

* Design Mongo Model
* Design GraphQL Schema
* Design React Component corresponding to each schema
* Design Box \(Grid Comp\) =&gt; Design Rows inside Box
* Place Box inside Main View



