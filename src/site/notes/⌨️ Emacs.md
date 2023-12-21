---
{"dg-publish":true,"permalink":"/emacs/"}
---

To use emacs, type:  `emacs filename`

To get help: `C-h r`
# Basic Commands  
## 🗃️ Open, Close, and Cancel 
| Binding | Action                       |
| ------- | ---------------------------- |
| C-x C-c | Close / Exit emacs           |
| C-x C-f | Open / find file             |
| C-x C-s | save window / buffer         |
| C-g     | Quit partially typed command | 

## 🗺️ Navigation 
| Binding    | Action                                  |
| ---------- | --------------------------------------- |
| C-b        | move back 1 char                        |
| M-b        | move back 1 word                        |
| C-f        | move front 1 char                       |
| M-f        | move forward 1 word                     |
| C-p        | move back 1 line                        |
| C-n        | move front 1 line                       |
| C-a        | move to front of line                   |
| C-e        | move to end of line                     |
| C-v        | move down 1 page                        |
| M-v        | move up 1 page                          |
| C-l        | scroll so current line is in the middle |
| add more?? |                                         |

## 📝 Text Editing 
| Binding              | Action                  |
| -------------------- | ----------------------- | 
| `<DEL>` - Delete key | backward delete 1 char  |
| C-d                  | forward delete 1 char   |
| M-d                  | forward delete 1 word   |
| C-x u                | undo 1 batch of changes | 
| C-k                  | kill / cut current line |
| C-w                  | cut selection           |
| M-w                  | copy selection          | 
| C-y                  | paste                   |

## 🔎 Search 
| Binding | Action                       |
| ------- | ---------------------------- |
| C-s     | incremental search forwards  |
| C-r     | incremental search backwards |
| M-%     | Query replace                             |
