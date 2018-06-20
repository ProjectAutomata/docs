### Component View

```
{
   _id: ShortID,
   payload:{
      type: view|widget|graph|activities|form,
      baseComponent: String,
      name: String
   }
}
```

### Component Setting

```
{
    _id: ComponentViewId:ShortId,
    payload:{
        panelId: String,
        //Check out the Panel Filter for more info.
        filter:[
             {
               queryType: and|or,
               dataType: String,
               type: contains,
               value: “XYZ”,
               panelPropId: 324242
             },
             {
               queryType: or,
               dataType: Date,
               type: is_within,
               To: “8/18/2017”
               From: “9/18/2017”,
               panelPropId: 324242
             },
             {
                queryType: or|and,
                dataType: Related
                relatedDataType: String|Date|other except Related add in validation. ,
                type: “contains| is_within depends upon the value of realtedDataType”,
                panelPropId: “”
                relatedPanelId: “Mongo id of related panel”,
                relatedPanelPropId: “MongoID of related panel’s property”
              },
             ....
             ....
        ]
    } 
}
```



