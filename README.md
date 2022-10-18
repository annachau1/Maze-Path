# Maze-Path

The purpose of this project is to implement a maze solving algorithm created by the Pyamaze package. Out of the different possible algorithms, we have decided to incorporate AStar into our currently running code, where we generated and displayed a maze, based on an input file. By using the AStar algorithm, it is able to identify the shortest path from the input start cell to the input goal cell. To learn more, please read further for more information on how this algorithm exactly works. For more clarification, please refer to the code comments or this video below.

https://www.youtube.com/watch?v=W9zSr9jnoqY&ab_channel=LearningOrbis

## Functionality of A
The overall AStar algorithm focuses around the concept of keeping track of three main values, f(n), g(n), and h(n), where f(n) = g(n) + h(n). By calculating these values for every surrounding cell relative to the start cell, the algorithm is able to decide which next cell (child cell), is the best option to the shortest path to the goal cell. 

## Calculating h(n)
H(n) can be calculated two ways. The first way is by looking at the maze generated by having an input file. Locate your start cell, and your goal cell. Use this grid as reference. From there, you want to connect these two cells by using an ‘L shape’. This L shape can be upside-down, backwards, right side up, or front facing. Counting the number of cells in between your start and goal cell (excluding the start cell and including the goal cell), you are able to find your heuristic score. Of course, this cannot be implemented into a coding language, but it may help with your interpretation of how the algorithm works. Below is an example of determining the heuristic score by eye. To calculate the heuristic score mathematically, we can take the absolute value of the subtraction of the x coordinates as well as the absolute value of the subtraction of the y coordinates, and lastly, sum these two absolute values together. This is now your heuristic score for the inputted start and end cell. 

## Calculating g(n)
In terms of g(n), this is what can be called, the cost of the path from the start cell. Essentially, starting from the start cell, where g(n) is 0, the possible surrounding cells would have a g(n) score of 0 (parent cell) + 1 (child cell). This concept applies to all child cells as the maze path is being solved. In other words, g(n) is the counter of how many steps will have to be taken to reach that certain child cell. 

## Calculating f(n)
Putting these two concepts together, g(n) + h(n), the equation of f(n) = g(n) + h(n) arises. This equation is calculated for every child cell encountered throughout the maze solving algorithm. Ultimately, the algorithm chooses its next cell step based on the LOWER f(n) value of the surrounding child cells. As it does this, the shortest path from the start cell to goal cell is found. 

## How AStar works with MazeGenerator algorithm
In order to allow the Astar algorithm to function, there must be a maze map to be solved. This maze map is generated by an input text file, which contains cell coordinates, and its respective distances from a wall based on the cardinal directions (E,W,N,S). Please refer to MazeGeneration to see more information on how the maze is generated. After the maze is generated, there is a dictionary containing the key: cell coordinate, and value: another dictionary of EWNS values of either 0 or 1. This dictionary is crucial to the AStar algorithm. In the AStar.py file, locate function findPath. In this function, as the maze path is being calculated, it reads from the dictionary and respectively calculates the new child cell f(n) values for each direction of the child cell. Therefore, the maze generated dictionary is crucial for AStar to perform properly. 

# Steps to be taken to demo AStar
# Choosing any start cell and goal cell
1. Download the following files:
        - AStar.py
        - example_a_star.py
        - pyamaze.py
        - inputfile.txt
2. Run example_a_star.py
3. View in terminal the shortest path coordinate system

# Choosing any goal cell but starting at only (4,4) with GUI DISPLAY
1. Download the following files:
        - AStar_GUI.py
        - pyamaze.py
        - inputfile.txt
2. Run AStar_GUI.py
3. View in terminal the shortest path coordinate system
4. A display should pop up with a red pointer showing the shortest path

