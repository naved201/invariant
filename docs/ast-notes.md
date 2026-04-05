# AST Notes

## What is AST?

AST stands for Abstract Syntax Tree. It is essentially a tree of Python objects that stores the high-level syntax inside a Python file. 

For example, as humans, we don't think about Python programs at the token level but rather in terms of high-level code blocks. AST does the same. It parses code scripts and stores document fields like the body. Within the body, it will store subfields like FunctionDef, For (for loop declaration) and its body. 

Code example:

for i in range(len(arr)):
    print(arr[i])

AST representation:
- For node
  - target: i
  - iter: Call(range)
    - argument: Call(len)
  - body:
    - Call(print)
      - argument: Subscript(arr[i])

## AST Methods

- ### NodeVisitor()
	It is a class offered by the ast module to traverse ASTs. 
	It has methods of the form:
	
	visit_<NodeType>
	
	which is called during runtime when the particular node type is encountered. It doesn't return or do anything by default unless specified by the developer.
	For example, visit_For will print the memory addresses of all for loop declarations from top to bottom within the Python file when defined as:

	```def visit_For(self, node): 
		print(node)
		self.generic_visit(node)```

	The node parameter is defined as node = ast.parse(example.py) inside the main function. 

	Traversal begins by calling:

	visitor.visit(tree)

	This walks the entire AST and automatically calls the appropriate visit_<NodeType> methods.	
