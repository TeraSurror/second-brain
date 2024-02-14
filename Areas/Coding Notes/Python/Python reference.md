##### Reading a file
```python
with open(file_name, 'rwa') as file:
	lines = file.read() # reads all the contents of the file and returns it as a string
```

##### Creating a default graph
```python
graph = {node: [] for node in graph_nodes}
```

