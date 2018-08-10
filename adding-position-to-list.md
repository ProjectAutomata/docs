## **Adding position to the list**

We will assign a position 65535 to first number and will get on adding 65536 to each number as it goes on increasing.

| List | Position |
| :--- | :--- |
| Item 1 | 65535 |
| Item 2 | 65535 + 65536 = 131071 |
| Item 3 | 131071+ 65536 = 196607 |
|  |  |

### Assigning a new position when dropping a list item between two list

Suppose a **Item 5** is being dropped in between **Item 2 **and** Item 3  
  
**

| List | Position |
| :--- | :--- |
| Item 1 | 65535 |
| Item 2 | 131071 |
| **Item 5** | **\(131071+196607\)/2 = 163839** |
| Item 3 | 196607 |



