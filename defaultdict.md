```
graph = defaultdict(set) means each value is a set? graph = defaultdict(list) means each value is a list?
```
```CPP
Yes, that's correct! In Python, the defaultdict class from the collections module allows you to specify the 
default value type for the dictionary.

When you create a defaultdict(set), it means that each value in the dictionary will be initialized with an empty 
set by default. For example:
```
```python
from collections import defaultdict

graph = defaultdict(set)
graph[1].add(2)
graph[1].add(3)
print(graph)  # Output: defaultdict(<class 'set'>, {1: {2, 3}})

To Print :
----------

for node, neighbours in enumerate(graph):
    if(len(neighbours) > 0):
        print(f"Node {node} has {len(neighbours)} neighbours : {', '.join(map(str, neighbours))}")
```
```CPP
Here, when you access a key that doesn't exist in the graph dictionary (e.g., graph[1]), it will create a new set 
as the value associated with that key and return it. So, you can directly call set methods like add() on the value
Similarly, when you create a defaultdict(list), each value in the dictionary will be initialized with an empty 
list by default. For example:
```
```Python
from collections import defaultdict

graph = defaultdict(list)
graph[1].append(2)
graph[1].append(3)
print(graph)  # Output: defaultdict(<class 'list'>, {1: [2, 3]})
```
```CPP
In this case, when you access a key that doesn't exist in the graph dictionary (e.g., graph[1]), it will create 
a new empty list as the value associated with that key and return it. So, you can directly call list methods like 
append() on the value.

By using defaultdict with set or list (or any other appropriate default value type), you can simplify the code by 
avoiding the need to explicitly handle the case of accessing non-existent keys and initializing them with the 
desired default value.
```
