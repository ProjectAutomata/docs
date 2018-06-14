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
        filter:[
             {
               queryType: and|or,
               dataType: String,
               type: contains,
               value: “XYZ”,
               panelPropId: 324242
             },
             ....
             ....
        ]
    } 
}
```



