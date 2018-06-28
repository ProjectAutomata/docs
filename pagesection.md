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



