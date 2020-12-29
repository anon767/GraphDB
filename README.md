# GraphDB

GraphDB is a graph database using SQLite3 for Python.
Check out [Recommendation Example](Recommendation.ipynb) for sample usage.

## Basic Usage

Create DB

```python
from GraphDB.GraphDB import GraphDB
db = GraphDB("test.sqlite")
```

Add node

```Python
db.add_node({'name': 'p1', 'type': 'person', "id": 1})
db.add_node({'name': 'p2', 'type': 'person', "id": 2})
```

Add edge

```python
db.add_ege(1, 2, {'action': 'likes'})
```

Draw Graph

```python
import networkx as nx
G = db.to_networkx()
nx.draw(G)
```

Get Edges with the property "action = features"

```python
eout = db.get_edges(source=5, predicate={'action': 'features'})
```

