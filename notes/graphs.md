Here's a small program for classifying properties of adjacency matrices. I don't think I have my transitive predicate defined correctly. I'd love to see if anyone can recommend a fix, or even produce a graph that will satisfy it the way it's written!

```python
from itertools import product

def make_graph_algebraically(nodes, predicate, z):
  adjacency= [[predicate(x, y, z) for x in nodes] for y in nodes]
  return adjacency

def divisible_predicate(x, y, z):
  if x == 0 and y == 0:
    return 1
  elif x == 0:
    return int(x / y == int(x / y))
  elif y == 0:
    return int(y / x == int(y / x))
  else:
    return int(x / y == int(x / y))

def mod_predicate(x, y, z):
  return int(x % z == y % z)

def order_predicate(x, y, z):
  return int(x >= y)

def sum_predicate(x, y, z):
  return int((x + y) == z)

word_map = {0: "zero", 1: "one", 2: "two", 3: "three", 4: "four", 5: "five", 6: "six", 7: "seven", 8: "eight", 9: "nine"}
  
def funky_predicate(x, y, z):
  return int(word_map[x] >= word_map[y] and (x < y))

def print_graph(nodes, graph):
  acc = "__| " + " | ".join([str(x) for x in nodes]) + " |\n"
  acc += "  |" + "===|" * len(acc[:-4:4]) + "\n"
  for i in range(len(nodes)):
    acc += str(nodes[i]) + " | " + " | ".join([str(x) for x in graph[i]]) + " |\n"
  return acc


nodes = list(range(10))
mod_graph = make_graph_algebraically(nodes, mod_predicate, len(nodes)/2)
order_graph = make_graph_algebraically(nodes, order_predicate, None)
sum_graph = make_graph_algebraically(nodes, sum_predicate, len(nodes)/2)
funky_graph = make_graph_algebraically(nodes, funky_predicate, None)
divisible_graph = make_graph_algebraically(nodes, divisible_predicate, None)

def is_reflexive(nodes, adjacency_matrix):
  result = True
  for i in nodes:
    result = result & bool(adjacency_matrix[i][i])
  return result


def n_tuples(nodes, n):
  return [x for x in product(nodes, repeat=n)]


def is_symmetric(nodes, adjacency_matrix):
  result = True
  pairs = n_tuples(nodes, 2)
  for pair in pairs:
    j, k = pair
    result = result & (adjacency_matrix[j][k] == adjacency_matrix[k][j])
  return result


def is_transitive(nodes, adjacency_matrix):
  result = True
  triples = n_tuples(nodes, 3)
  for triple in triples:
    l, m, n = [nodes.index(x) for x in triple]
    result = result & (adjacency_matrix[l][n] if adjacency_matrix[l][m] == adjacency_matrix[m][n] else True)
  return result


print(print_graph(nodes, order_graph))
print(print_graph(nodes, sum_graph))
print(print_graph(nodes, mod_graph))
print(print_graph(nodes, funky_graph))
print(print_graph(nodes, divisible_graph))

def check_predicates(adjacency_matrix):
  return (is_reflexive(nodes, adjacency_matrix), is_symmetric(nodes, adjacency_matrix), is_transitive(nodes, adjacency_matrix))


summary_matrix = {x[0]: check_predicates(x[1]) for x in (["order_graph", order_graph], ["mod_graph", mod_graph], ["sum_graph", sum_graph], ["funky_graph", funky_graph], ["divisible_graph", divisible_graph])}
names = ["reflexive", "symmetric", "transitive"]

def print_summary(summary_matrix):
  name_max = max([len(x) for x in summary_matrix])
  acc = " " * name_max + " | " + " | ".join(names) + " |\n"
  for sm in summary_matrix:
    r, s, t = summary_matrix[sm]
    acc += sm + " " * (name_max - len(sm)) + " | " + f" {int(r)}" + " " * (len("reflexive") - 2) + " | " + f" {int(s)}" + " " * (len("symmetric") - 2) + " | " + f" {int(t)}" + " " * (len("transitive") - 2) + " |\n"
  return acc


print(print_summary(summary_matrix))
```