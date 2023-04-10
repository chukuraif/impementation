# impementation
Two Implementation task
def mat_to_list(adj_mat):
    n = len(adj_mat)
    adj_list = [[] for i in range(n)]
    for i in range(n):
        for k in range(n):
            if adj_mat[i][k] == 1:
                adj_list[i].append(k)
    return adj_list
adj_mat =   [[0, 1, 0, 1, 0, 0],
             [0, 0, 1, 0, 0, 0],
             [1, 0, 0, 0, 0, 0],
             [0, 0, 0, 0, 1, 0],
             [0, 0, 0, 1, 0, 0],
             [0, 0, 0, 0, 0, 0]]
adj_list = mat_to_list(adj_mat)
print(adj_list)

def reachable(adj_list, start_node):
    def dfs(node, visited):
        visited.add(node)
        for neighbor in adj_list[node]:
            if neighbor not in visited:
                dfs(neighbor, visited)
                
    visited = set()
    dfs(start_node, visited)
    return visited

adj_list = [[1, 3], [2], [0], [4], [3], []]

start_node = 0
reachable_nodes = reachable(adj_list, start_node)
print("Nodes reachable from node", start_node, ":", reachable_nodes)

start_node = 3
reachable_nodes = reachable(adj_list, start_node)
print("Nodes reachable from node", start_node, ":", reachable_nodes)
