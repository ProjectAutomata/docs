# Panel

![](/assets/AutomataWork %281%29.png)

#### 

#### Design Flow:

#### ![](/assets/DesignFlow.png)

## Introduction:

1. Each **Project** will have many **Panels**.

2. Each **Panel** will have many **Pages**.

3. Each **Page** will have many **Components.**

4. Each **Component **will be associated with a **componentView** model and **ComponentACL**.

5. **ComponentView** model will contain all the setting that is needed for a perfect Grid/Widget/Graph etc to display.

### Panel

A panel will have following options:  
A panel will have a `type`  like `data|dashboard|etc.`

A panel will have following options:

1. Add Properties/Validation/ACL of Properties
2. Pages
   1. Create/Edit a Page.
   2. Set a page as **default.**
   3. Rename a page.
   4. Delete a page.
   5. Assign Components:
      * Drag and Drop Components to a Page View area.
      * Adjust Size and Position of Components in the View.
      * Remove a Components from a View.
      * Add Some basic Grid Related features like autoheight, fixed during component assignment.
   6. 

#### ComponentView Model

**When type === "view" and viewType === "grid":**

```js
{
    type: view| widget|graph|activities|form,
    viewType: grid|kanban|gallery|calendar|analytics|timeline|compare|other,
    widgetType: simple|multirowcolumn,
    graphType: bar|line|gaugemeter|radar|pile|polar,
    label: String,
    projectId,
    panelId,
    baseComponent: String,
    viewOptions:{
        addData:[
            {
                id: UUID,
                label: String,
                description: String,
                coordinates:{ x: Number, y: Number, w: Number, h: Number },
                maxWidth: Number,
                minWidth: Number,
                maxHeight: Number,
                minHeight: Number
            }
        ],
        rows:[
            {
                cells:[
                    {
                        panelPropId: String,
                        style:{
                            //All style related data.
                        },
                        componentName: String,
                        componentOption:{
                            //Component Related Option...
                        },
                        label: String,
                        showHelp: Boolean,
                        readOnly: Boolean: default: false
                    }
                ]
            }
        ],
        tables:{
            //PanelProp Id of the current Panel.
            "#panelPropId": {
                display: Boolean|default:true,
                label: String| "Optional",
                position: Number| "Optional"
            }
        },
        rules:{
            defaultRuleId: "MongoObject"| "Optional", //Default id of panelRule if provided.
            where:[],
            sort:[]
        },
        showRulesOnHeader: Boolean| default: true
    }
}
```

#### Tasks List \(Work Need To Be Done\)

* [ ] Panel Attached with Grid View
* [ ] Panel Grid View Edit Screen
* [ ] Add new data screen
* [ ] Delete a Row
* [ ] Edit Row
* [ ] Multiple Views Support
* [ ] Run Time implementation of filter. Like a data value is changed then at that time it will check whether it confronts to any of the active filter and will get hidden or displayed based on the filter applied all condition will happen at run time only.
* [ ] Ctrl+Z implementation to undoing the last performed action. Upto 1 or 2 permissible limit only.
* [ ] CTRL + R to redo the action.

* [ ] Assigning Route to Panel

* [ ] Panel Detail Design and Logic

* [ ] Settings -&gt; Import _\(Currently not supported will import all project\)_

* [ ] Setting -&gt; Export _\(Currently not supported will export all project\)_

* [ ] Setting -&gt; Print

* [ ] Setting -&gt; Help

* [ ] Display bottom footer displaying total time taken to fetch the data from server.

#### Total Time

| Features | Screens | Design Time | Logic Time | Priority |
| :--- | :--- | :--- | :--- | :--- |
| Add New Data |  |  |  |  |
| Delete Data |  |  |  |  |
| Assign Subscriber |  |  |  |  |
| Settings |  |  |  |  |
| Panel Details |  |  |  |  |
| Sort |  |  |  |  |
| Filter |  |  |  |  |
| Route |  |  |  |  |
| Views |  |  |  |  |
| Edit |  |  |  |  |

#### Screens

| Name | Comment |
| :--- | :--- |
|  |  |

#### 



