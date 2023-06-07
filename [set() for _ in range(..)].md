```
How to create a list of empty sets ? list size = 5
```
```python
graph = [ set() for _ in range(5) ]
```
```PYTHON
To Add :
--------

graph[0].add(1)
graph[0].add(2)
graph[1].add(3)
graph[1].add(3)

To Print :
----------

for node, neighbours in enumerate(graph):
    if(len(neighbours) > 0):
        print(f"Node {node} has {len(neighbours)} neighbours : {', '.join(map(str, neighbours))}")
```