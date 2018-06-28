    //PageSection
    {
      _id: {
          type: String,
          parent: true,
          trim: true,
          description: "_id will be formed by `pageId:::shortId`"
      },
      pageId: {
        type:  String, ref: 'Page',
        required: true,
        trim: true,
        //Index is required here..
        index: true
      },
      screenType:{
        type:  String,
        required: true,
        default: 'large',
        trim: true,
        enum:["large", "small", "medium"]
      },
      //Will define priority
      position:{
        type:  Number
      },
      columns:[
        {
          //TODO: Change it to width..
          column:  {
            type: Number,
            required: true,
            min: 1,
            max: 16
          },
          config:Mixed,
          componentViewId: {
            type: String,
            ref: 'ComponentView',
            required: true
          }
        }
      ]
    }

**Steps to add Component View to a Section and Section to a Page.**

Section is like a row on a page which will have 16 columns.

1. Create Component View
   1. ```
      mutation{
        componentView{
          create(
            type:"view", 
          	viewType:"grid",
            label:"GridViewComponent",
            projectId: "Skvz2f-bX",
            baseComponent:"GridView",
      
          ){
            id,
            viewType,
            label,
            projectId,
            baseComponent
          }
        }
      }

      //Response
      {
        "data": {
          "componentView": {
            "create": {
              "id": "Hkt_2fzGX",
              "viewType": "grid",
              "label": "GridViewComponent",
              "projectId": "Skvz2f-bX",
              "pageId": null,
              "baseComponent": "GridView"
            }
          }
        }
      }

      ```

      2. Create Page Section.

      1. ```
         mutation{
           pageSection{
             upsert(
               pageId:"Skvz2f-bX:B1bDVzGM7::B1xZPVzffm", 
               position:1, 
               screenType:"large", 
               columns:[
                 {
                   column:16,
                   componentViewId:"Hkt_2fzGX"
                 }
               ]){
               id,
               screenType
               position,
               columns{
                 column,
                 componentViewId,
                 componentView{
                   id,
                   type,
                   viewType,
                   label
                 }
               }
             }
           }
         }


         //Response..
         {
           "data": {
             "pageSection": {
               "upsert": {
                 "id": "Skvz2f-bX:B1bDVzGM7::B1xZPVzffm:::SyUnnMMfX",
                 "screenType": "large",
                 "position": 1,
                 "columns": [
                   {
                     "column": 16,
                     "componentViewId": "Hkt_2fzGX",
                     "componentView": {
                       "id": "Hkt_2fzGX",
                       "type": "view",
                       "viewType": "grid",
                       "label": "GridViewComponent"
                     }
                   }
                 ]
               }
             }
           }
         }
         ```







