import itertools

NO_PATH = float('inf')
graph = [[0, 7, NO_PATH, 8],
         [NO_PATH, 0, 5, NO_PATH],
         [NO_PATH, NO_PATH, 0, 2],
         [NO_PATH, NO_PATH, NO_PATH, 0]]
MAX_LENGTH = len(graph[0])


def floyd(distance):
    """
    A recursive implementation of Floyd's algorithm
    """

    def shortest_path(start_node, end_node, intermediate):
        # Base case: all intermediate vertices have been considered
        if intermediate == MAX_LENGTH:
            return distance[start_node][end_node]
        # Update the shortest distance between start_node and end_node
        distance[start_node][end_node] = min(distance[start_node][end_node],
                                             distance[start_node][intermediate] + distance[intermediate][end_node])
        # Recursive case: move on to the next intermediate vertex
        return shortest_path(start_node, end_node, intermediate + 1)

    # Iterate over all pairs of vertices
    for start_node in range(MAX_LENGTH):
        for end_node in range(MAX_LENGTH):
            # If start_node and end_node are the same, the distance is zero
            if start_node == end_node:
                distance[start_node][end_node] = 0
                continue
            # Update the shortest distance between start_node and end node using all intermediate vertices
            shortest_path(start_node, end_node, 0)

    # Print each row of the distance matrix on a separate line
    for row in distance:
        print(row)

floyd(graph)
