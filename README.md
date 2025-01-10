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

The end results sugest the routes when applying Manhattan or Chebyshev metrices and how we can improve them.

## Data Description
The data table shows nodes coordinates in which 0 represent a depot and the rest are customers' locations. Find the tour that starts at depot then visits all the customers and return back to depot. We are going to use three Heuristics approaches, which are Nearest Neighbor, Cheapest Insertion and then Improvement Heuristic:

(1) Assumming that the cost to travel between any pair of nodes is conducted by the Manhattan metric.

(2) Assumming that the cost to travel between any pair of nodes is conducted by the Chebyshev metric.

(3) Apply 2-opt Improvement technique to find the new set of solutions.

<img width="183" alt="image" src="https://github.com/user-attachments/assets/ce194d52-3574-4909-9064-e181e7aa43c6" />

## Algorithm Implementation

I am going to use pandas, numpy and matplotlib.pyplot for this example. Here is step by step how we implement the logic.

1. Distance Calculation
   Two distance matrices are created. These matrices represent the cost of traveling between nodes using the respective metrics:
   - l1_distances for Manhattan (L1 norm).
   - max_distances for Chebyshev (L∞ norm).
     
2. Heuristic Methods:
   - Nearest Neighbor (NN): Selects the nearest unvisited node at each step for both Manhattan and Chebyshev metrics.
   - Cheapest Insertion (CI): Inserts nodes into an existing tour at the position that minimizes the increase in total cost and used for both Manhattan and Chebyshev metrics.
     
3. Tour Cost Calculation:
   get_tour_cost calculates the total cost of a tour based on the chosen metric (Manhattan or Chebyshev).
   
4. Improvement Method using 2-opt improvement:
   Implemented for tours generated using both metrics and heuristics (NN and CI) by using a local search heuristic that attempts to optimize the current tour by swapping edges to reduce the tour length.
   
5. Output:
   - The total cost of the tour for the Nearest Neighbor and Cheapest Insertion heuristics using both Manhattan and Chebyshev metrics.
   - Improved tours using the 2-opt heuristic for all combinations of metrics and initial heuristics.

## Result

![image](https://github.com/user-attachments/assets/8f49f594-b6d1-44c6-97a0-f907bf66ba3d)


![image](https://github.com/user-attachments/assets/60c2cf66-92cf-41f4-8314-3125dfb8f7d5)

