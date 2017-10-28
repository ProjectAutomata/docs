# Activities

![](/assets/AutomataWork %285%29.svg)

## Maintaining Hook - Component - State Flow In a Activity

![](/assets/AutomataWork %286%29.svg)

Concept all the components will be an activity.

Each activity while registering to **BaseComponent **will also register for its component and hooks.  
Each baseComponent will have a method for fetching component by name and hook by name.

On Page load it will first fetch its BaseComponets and after fetching its baseComponents each components will checkout for its hooks present on its page. If hook present then patient will request a backend api calling for its patients list and will fetch its view and then attach its view to its respective Hooks.

#### Required Engines

1. Activity Register Engines
2. Activity Design Engine
3. Activity Execution Engine

#### Remote Hooks

1. Define several unique Id for all the remote hooks defined.
2. Each hooks will corresponds to a particular view area of a state.
3. Define Complete Application into a groups of unique states.
4. Thus each state will have several hooks area where adding an activities will get adhere to that position.
5. Each activities will be designed inside \`baseComponents``folder and will get registered in `component-config.json` as activities``
6. All Base Components will have a type, permission and hooks and components with view, register.
7. Based on hooks & state a Base Components displays several activity , widget, graph or Panel Views etc.
8. Each page will load it state and state will load its components each componenents after load will check for its hooks and will load its hooks.

### Activities Tasks

1. [ ] Design all required engined required for activity.
2. [ ] Design method in base component how to define a base component of type activity.
3. [ ] Add various type of base component

> > > Activity
> > >
> > > Widget
> > >
> > > Graph
> > >
> > > Panel Views
> > >
> > > Dashboard Views

1. [ ] Define \`state\` for all available pages.
2. [ ] Define \`hooks\` for all availaible status where a activity UI will get placed.
3. [ ] Hook will be for all Panel view, Activities, Graph
4. [ ] Show All Activities Permission while registering with hooks. Like Email -&gt; Read, Execute, Write
5. [ ] Panel Activities Like -&gt; Invoice Activities

6. [ ] Panel Activities Like -&gt; Mass Email Activities

7. [ ] Panel Activities Like -&gt; Work Automatation

8. [ ] Panel Activities Like -&gt; Sales Automation

9. [ ] Panel Activities Like -&gt; TODO
10. [ ] Security Page to display all installed activity lists.

#### Total Time

| Features | Screens | Design Time | Logic Time | Priority |
| :--- | :--- | :--- | :--- | :--- |
| Design all required engines for activity |  |  |  |  |
| Method in Base Component and how to defined base component of type activity |  |  |  |  |
| Define  hooks and types of baseComponenet during register. |  |  |  |  |
| Register for permission a Activity possess. |  |  |  |  |
| Mass Email | 1 |  |  |  |
| Invoice Activities | 1 |  |  |  |
| Work Automation | 2 |  |  |  |
| Sales Automation | 2 |  |  |  |
| TODO | 1 |  |  |  |
| Call Track | 1 |  |  |  |
| Setting Page for displaying all installed activity and option to disable it. | 1 |  |  |  |

#### Screens

| Screen | Comment | Merge Status |
| :--- | :--- | :--- |
| Activity\_Mass\_Email |  |  |
| Activity\_Invoice\_Activities |  |  |
| Activity\_Work\_Automation |  |  |
| Activity\_Sales\_Automation |  |  |
| Activity\_TODO |  |  |
| Activity\_Call\_Track |  |  |
| Activity\_Setting\_Page |  |  |

#### 



