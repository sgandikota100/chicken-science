---
{"dg-publish":true,"permalink":"/matlab/"}
---

Just a list of basic commands in one neat place 😅 
## Basic Syntax + Management
| Command         | Function                                                        |
| --------------- | --------------------------------------------------------------- |
| `save file.mat` | save file; to save 1 variable, add the variable after the space |
| `clear`         | clears workspace                                                |
| `load file.mat` | opens file in the workspace                                     |
| `variable`      | displays content of variable                                    |
| `clc`           | clears command window                                           |
| `format`        | can adjust no. of decimals (either `long` or `short`)           |
| `doc`           | opens documentation about a function                                                                |

## Arrays, Vectors, + Matrices
- `[# #]` = creating an array 
	- `[#;#]` = creates a column vector 
	- `[#:#]` = creates evenly spaced vectors 
	- `[#:no.:#]` = specifies a different spacing 
- `linespace(first,last,number_of_elements)` = array function
- `'` = transposes row to column vector (array)
	- ie `x = (1:2:5)'`
- `rand(#)` = creates a random matrix 
	- `(#)` = \#-by-# square matrix 
	- `(#, #)` = creates a rectangular matrix
- `zeros()` or `ones()` = matrix of only 0s or 1s
- `size()` = determines size of existing matrix
- `variable = file(#, #)` = extract a value with row-column indexing
	- `end` = keyword for last row or column; can do + / - # 
	- `:` = all elements in that dimension or a range of values
		- ie `x = A(1:3,:)` means rows 1 - 3,  and all columns 
- `file(index_value)` = indexing for a single index value 
- `array + #`  = array addition 
- `array *\/ #`= multiply or divide by scaler 
- `*` = matrix multiplication with EQUALLY sized vectors 
- `*.` = performs element-wise multiplication 
- `[dr,dc] = size(file)` = creates separate variables that store row and column 
- `~` = ignores first output
## Plotting Data 
- `histogram(var,"FaceColor", "color")` = plots histogram with color bars 
- `plot(x,y)` = plots vectors of the same length
	- `(x,y "specs")` = add specifications about lines, found [here](https://www.mathworks.com/help/matlab/ref/plot.html#btzitot_sep_mw_3a76f056-2882-44d7-8e73-c695c0c54ca8)
	- `(variable,"LineWidth",#)` = ploting with line width
- `hold on` = plot one line on top of another in same axes
- `hold off` = return to default behavior
- `title("name")` = title of plot 
- `ylabel()` or `xlabel()` = label x or y axis
- `legend("a","b","c")` = add legend in specified order
- `+` = use to joing plot annoation values 
	- ie `title("Sample " + sample(3) + " Data")` 
## Importing Data 
- `table.VarName` = extract a variable from a table
- sort table = click on table and select sort... 
## Logical Indexing 
Use redional operatiors to perform comparisions( `<, >, ==, ~=` ), resulting in 1 (true) or 0 (false) 
- `var = var1(var1 > #)` = creates logical array 
- `var(varOPS#) = #` = replaces number that meets condition 
- `&, |` = logical operators "and", "or"

## Programming 
1. if-else: The body of an if block executes only if the condition is true 
```
x = rand
if x > # 
	y = 3 
else 
	y = -3
end
```
2. for: the loop executes as specified through the loop counter (c)
```
for c = 1:3
	disp (c)
end
```