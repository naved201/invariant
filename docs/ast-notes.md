# AST Notes

## What is AST?

- AST stands for Abstract Syntax Tree. It is essentially a JSON object that stores the high-level syntax inside a Python file. 

For example, as humans, we don't think about Python programs at the token level but rather in terms of high-level code blocks. AST does the same. It parses code scripts and stores document fields like the body. Within the body, it will store subfields like FunctionDef, For (for loop declaration) and its body. 
