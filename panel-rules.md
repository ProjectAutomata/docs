### Panel Rules Design Docs

#### Panel Filter

```
{
    _id: 1,
    payload:{
        name: 'panel filter name',
        panelId: 'panel filter id',
        where:[
            {
                queryType: and|or,
                dataType: string|number|date|boolean|related|enum,
                type: contains etc..
                value: 'data',
                panelPropId: 3
            }
        ]
    }
}
```

```
if dataType === String:
    contains
    does_not_contains
    is
    is_not
    is_empty
    is_not_empty

if dataType === Number
    contains
    does_not_contains
    is
    is_not
    is_empty
    is_not_empty
    gt
    lt
    gte
    lte

if dataType === Date
    is
    is_within
    is_before
    is_after
    is_on_or_before
    is_not
    is_empty
    is_not_empty

if dataType === Boolean
    is

if dataType === Related
    Depends on the type of panel props
if dataType === enum
    1. Display dropdown
    2. is
    3. is_not
    4. is_empty
    5. is_not_empty
```

### **PANEL FILTER FUTURE ROADMAP**

1. ### **Advance filter option like**
2. 1. **We can apply filter like**

   2. 1. **Show only those data whose quantity x rate is greater than 100**

      2. **Show only those dataamount - discount &gt; 100**

      3. **Or we could also move it to a new window screen.**
3. **Enum Grouping Option like**

4. 1. **If a property example country:**

   2. 1. \*\*then we can calculate the group of the country and display it list of country in the filter as we do for enum.  
         For more info check“market type filter for ZOHO CRM”\*\*
5. **Add Last Week, This Week, This Month for Date. \(Do it now\)**



