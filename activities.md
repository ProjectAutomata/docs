# Activities

![](/assets/AutomataWork %285%29.svg)

## Maintaining Hook - Component - State Flow In a Activity

![](/assets/AutomataWork %286%29.svg)

Concept all the components will be an activity.

Each activity while registering to **BaseComponent **will also register for its component and hooks.  
Each baseComponent will have a method for fetching component by name and hook by name.

On Page load it will first fetch its BaseComponets and after fetching its baseComponents each components will checkout for its hooks present on its page. If hook present then patient will request a backend api calling for its patients list and will fetch its view and then attach its view to respective Hooks.



