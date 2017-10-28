# Import

![](/assets/AutomataWork %2810%29.svg) .

#### Explanation

##### Project

1. Import a complete project and property/history etc.
2. Format extensions will be defined by Automata.
3. Only file downloaded as a backup version for import can be used as import feature for a project.
4. If a project is already present and its backup file is getting imported. Then on import will get discarded in that case.
5. An Imported project will contain backup of all the panel etc.

### Tasks for Project Import

* [ ] Uploading of a file Engine
* [ ] Schema format parser engine
* [ ] Design rules for uploading backup files.
* [ ] Design schema parser using Lex and parse.
* [ ] To Upload documents dump all mongodb data present in file to database. Including an Activity, Components etc.
* [ ] Decrypt file before uploading JSON file using CRYPTO.
* [ ] Veriify file integrity using SHA before uploading it as any tempered document can also corrupt complete documents.
* [ ] Also create new IDs of all documents before inserting new data.

### Tasks for Panel Import

* [ ] Upload data using ".csv" and excel
* [ ] Engine required.
  1. Data format Parser
  2. Data uploader
  3. Data Validator.

#### Total Time

| Features | Screens | Design Time | Logic Time | Priority |
| :--- | :--- | :--- | :--- | :--- |
| Uploading of a file | 1 | 4 | 3 |  |
| Schema of format parser engine |  |  | 6 |  |
| Rules for uploading backup files |  |  | 4 |  |
| Schema parser using Lex and parse |  |  | 2 |  |
| Decrypt file and check integrity of files |  |  | 1 |  |
| Upload all the imported files to database |  |  | 8 |  |
| Import data of a Panel using .CSV  and excel format file | 1 | 4 |  |  |

#### Screens

| Screen | Comment | Merge Status |
| :--- | :--- | :--- |
| Import\_Project\_Upload |  |  |
| Import\_Panel\_Upload |  |  |





