# Travelling-Salesman-Problem-(TSP)-with-Manhattan-and-Chebyshev Metrices
TSP is a classic optimization problem that poses the challenge to find the shortest rounded trip. The route must visit all the cities and return to the original city. This problem is a real life application for many business cases such as logistic (delivery route), network design (minimize power cable lengths), manufacturing (optimize equipment operations), etc.

There are many approaches to solve TSP such as:
1. Exact Methods: Brute Force by enumerate all possible routes and calculate their lenghts then select the shortest, Dynamic Programming, Integer Linear Programming.
2. Heuristic Methods: Nearest Neighbor, Cheapest Insertion, Minimum Spanning Tree, Improvement Heuristic.
3. Metaheuristic Methods: Strategies that guide heuristic to escape the local optima to explore global optima solutions such as Simulated Annealing, Genetic algorithm, Ant Colony Optimization.

In this post, I am using heuristic - nearest neighbor method - by applying Manhattan and Chebyshev metrices as distance measures. Then we will improve them.
1. Manhattan Metric is also known as Taxicab distance, calculate the distance between two points by summing the absolute deltas of their coordinates. it's often used when travelling in straight lines such as the grid-like street layout ot Manhattan (no diagonal).
2. Chebyshev Metric calculates the distance between two points based on the maximum of the absolute deltas of their coordinates. It's used when diagonal movement is allowed.
3. Improvement Heuristics can modify an existing solution to improve its quality. The techniques are 2-opt, 3-opt, k-opt by swapping, removing or reconnecting the edges. I am using 2-opt for this example.

## Data Description


<img width="183" alt="image" src="https://github.com/user-attachments/assets/ce194d52-3574-4909-9064-e181e7aa43c6" />


## Network Design Visualization

## Algorithm Implementation


## Result
