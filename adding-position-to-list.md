## **Adding position to the list**

We will assign a position 65535 to first number and will get on adding 65536 to each number as it goes on increasing.

| List | Position |
| :--- | :--- |
| Item 1 | 65535 |
| Item 2 | 65535 + 65536 = 131071 |
| Item 3 | 131071+ 65536 = 196607 |
|  |  |

### Assigning a new position when dropping a list item between two list

Suppose a **Item 5** is being dropped in between **Item 2 **and **Item 3**

| List | Position |
| :--- | :--- |
| Item 1 | 65535 |
| Item 2 | 131071 |
| **Item 5** | **\(131071+196607\)/2 = 163839** |
| Item 3 | 196607 |

###  Special Case:

When adding two List item **List 1\(65535\) and List 2\(\(131071\)** and then  Archiving **List 2 **and again adding a new item List 3\(131071\).  
  
Note: Here list 3 will get same position as List 2 because at the time of adding **List 3\(131071\) `List Item 2` was already archived.  
  
Now undoing the archiving of List Item 2  In that case both List 2 and List 3 will have same position -&gt; 131071.  
  
Now when dropping a new Item `List 4` between `List 2` and `List 3` We have to change the position of List 3 as both will have same position hence a special case will get handled.  
  
**  




