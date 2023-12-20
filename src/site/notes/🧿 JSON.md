---
{"dg-publish":true,"permalink":"/json/"}
---

**JavaScript Object Notation** is a text format for storing data in strings based on javascript. 
# Format
`""` - denotes a *key* or literal *value*
`{}` - denotes an *object*
`[]` - denote an array 

# An Example 
Here's a JSON-formatted string constructed with Java: 
```java 
String nl = "\n";
String jsonString = "{     " + nl
    + "  \"name\": \"Jay\"," + nl
    + "  \"age\": \"19\",  " + nl
    + "  \"classes\": [    " + nl
    + "    \"CSCI 1302\",  " + nl
    + "    \"CSCI 1730\"   " + nl
    + "  ]                 " + nl
    + "}                   ";
System.out.println(jsonString);
```
Here's the output, formatted in JSON: 
```json
{
  "name": "Jay",
  "age": "19",
  "classes": [
    "CSCI 1302",
    "CSCI 1730",
    "CSCI 2610"
  ]
}
```
