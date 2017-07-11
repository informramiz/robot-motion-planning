# robot-motion-planning
A python program to plan the motion of a robot. This is simple and basic problem. A robot has to go from start location to an end location in a maze with minimum cost possible. A robot can go left, right, up and down and performing each step costs 1. It can be seen in a picture below.

![visualization.png](visualization.png)

At the end the program prints the `final path` and `cost` or if it was not able to reach destination then it prints `fail`.

The code is divided into 3 parts.

1. Search by trying every possible node to find optimal path.
2. Optimized search using heuristic function input, from a given starting cell to a goal cell.
3. Optimized search using dynamic programming which gives optimal path from every possible starting cell to a goal, not just from a given starting cell like in `A*`.


## Using Heuristic Function to Optimize Search

The heuristic function is a way to inform the search about the direction to a goal. It provides an informed way to guess which neighbor of a node will lead to a goal. There is nothing magical about a heuristic function.

![A*](A_star.png)

As heuristic function gives an estimated guess of distance of current cell from the goal cell so we can use that to improve our search. Now instead of picking cells with minimum cost (also called g-value), we are going to pick cells with minimum f-value (g-value + h(x, y)) where h(x,y) gives the distance from cell (x, y) to goal cell.

## Dynamic Programming

`A*` only gives you optimal solution from a given cell to the goal cell but `Dynamic Programming` gives you optimal path to goal cell from any source cell. 

![Dynamic Programming](dynamic-programming/dp.png)

- **Policy** tells you an optimal action (go up, down, left, right on maze) to perform given a cell. Below is a visualization of that taken. 

![Policy](dynamic-programming/policy.png)

- **Value Function**, for each cell, tells you the length of the shortest path to the goal from that cell. Below is a visualization of that. 

![Policy](dynamic-programming/value-function.png)
