# Simple Adjacency-Set Graph Datastructure Implementation

## Motivation

Common Graph datastructures suffer from performance bottlenecks. For example in Adjacency Matrix
datastructures the check whether there exists an edge between two vertices/nodes takes
$\mathcal O(n)$ time and the addition adn removal of nodes is not really possible without moving
whole the quadratic memory footprint of the matrix around.

On the other hand, Adjacency Lists do not make things much better as the removal of a node costs
still $\mathcal O(n + m)$ time since we first need to find the node and remove all incident edges.

An Adjacency-Set-based datastructure can provide better modifability, since access times for edges
and nodes are always constant.

## Time Complexity

| Method        | Time Complexity             |
|---------------|-----------------------------|
| `add_node`    | $\mathcal O(1)$             |
| `add_edge`    | $\mathcal O(1)$             |
| `remove_node` | $\mathcal O(\deg(v))$       |
| `remove_edge` | $\mathcal O(1)$             |
| `constructor` | $\mathcal O(\|V\| + \|E\|)$ |

__NOTE:__ For most search tasks (DFS, BFS, Dijkstra's Algorithm) an Adjacency List approach will
still be faster, since there is less overhead introduced compared to the set datastructure. The
adjacency set approach is merely an alternative with "good" _theoretical_ time complexity
properties.

## Implementation

This datastructure is relatively unoptimized for didactic purposes. The aim is to provide a clean,
working implementation of an Adjacency-Set graph datastructure in the C++ language. The
implementation uses `std::unordered_map` for the set of nodes, the set of edges and each node's
neighbour relations.

### Project Structure

The whole graph datastructure is contained in the files `adj_set_graph.h` and `adj_set_graph.cpp`. The file `main.cpp` contains some example code on how to construct such a graph. If you would like to use this datastructure for your project, all you need are the first two mentioned files.

### Future Work

In the future, I might add functionality to read an write to common graph formats, so this program could be used as a converter between formats as well as the functionality to perform different graph algorithms on the graph as a command line tool.

## License

This project is published under the __GPL v3 license__ included in `license.txt`.