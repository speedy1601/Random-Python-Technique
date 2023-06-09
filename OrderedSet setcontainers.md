[OrderedSet](https://www.udacity.com/blog/2021/11/python-ordered-sets-an-overview.html)
[setcontainers](https://www.geeksforgeeks.org/python-sorted-containers-an-introduction/)
## SortedDict( )
### graph = SortedDict( )

## Adding built-in data type
```
graph['A'] = 10
```
## Adding custom data type where the custom data type in especial sorted order
```Python
class edge :
    def __init__(self,to:str, cost:int):
        self.to = to
        self.cost = cost
    def __lt__(self, other):
        return (self.to, self.cost) < (other.to, other.cost)

def main():
    graph = SortedDict()
    from, to, cost = 'USA', 'Germany', 20
    graph.setdefault(fromm, SortedSet())
    graph[from].add(Edge(to, cost)) 
          
In the code graph.setdefault(fromm, SortedSet()), the setdefault() method is used to retrieve the value for the 
given key fromm from the graph dictionary. If the key is present in the dictionary, the method returns its 
corresponding value. If the key is not present, the method sets the key to the default value provided (SortedSet() 
in this case) and returns that default value.    
So here it's returning the empty set if the key(fromm) doesn't exist OR the existing set if key(fromm) exists.
any set.add(value) is how to to insert value in set. 
Instead of writing graph.setdefault(fromm, SortedSet); graph[from].add(Edge(to,cost)); Just write in a single line 
graph.setdefault(fromm, SortedSet()).add(Edge(to, cost)) == set.add(Edge(to, cost))  
```
```CPP
You can't write graph = SortedDict(SortedSet) BUT graph = defaultdict(sorted) because -

defaultdict is a subclass of dict that automatically creates and initializes a new entry with a default value if the 
key doesn't exist when accessed. The defaultdict implementation doesn't rely on key comparisons or sorting, so it can 
use SortedSet as the default value without any issues.

On the other hand, SortedDict in the sortedcontainers library is specifically designed for maintaining a sorted order
of keys. It requires a comparison function or key function to determine the ordering of the keys. It doesn't directly
support nested sorted containers like SortedSet as the value type. Therefore, using SortedSet directly as the value 
type for SortedDict won't work as expected.
```