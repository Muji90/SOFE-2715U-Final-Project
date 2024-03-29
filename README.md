# <ins>SOFE-2715U-Final-Project</ins>
Data Structures (SOFE 2715U) Final Project

| Names  | Student Numbers |
| ------------- | ------------- |
| Ejiroghene Emmanuel Emore   | 100827336  |
| Sajid Vijayan  | 100820701  |
| Muhammad Mujtaba Madad  | 100790195  |

# <ins>Background</ins>
Mazes have been a popular form of entertainment and mental challenge for centuries. One way to construct a maze is by starting with an n×n grid and removing walls to create a path from a start to a finish. In this project, we will use a different method of constructing mazes by assigning random values to walls and finding a minimum spanning tree of a graph constructed from the dual of the maze grid. The goal of this project is to write a program that uses the algorithm described above to generate mazes and solve them. The program will generate a maze of its own and ideally visualize the solution. The program will be written in a modern programming language such as JAVA and will make use of data structures and algorithms to efficiently generate and solve mazes.

# <ins>Description</ins>
This project aims to create a program that can generate and solve mazes using a unique algorithm. Instead of starting with an empty grid and removing walls to create a path from a start to a finish, we will assign random values to walls and construct a graph from the dual of the maze grid. We will then find a minimum spanning tree of the graph and remove walls corresponding to the edges in the tree, resulting in a maze that can be solved using a graph traversal algorithm.

# <ins>Maze Generator</ins>

The maze we made gives the users the oppurtunity to also make their own maze if they desire to while also try and solve an unlimited amount of mazes. The user has to ability to generate a full maze once they press the 'Randomized Maze' button and once they are finished completing the maze they have to ability to regenerate a new maze and complete that. The user has the ability to do this an unlimited number of times as shows in the three images below. Each maze is generated after clicking on the 'Randomized Maze' button once the user has completed a maze. Note that the maze startes from the left side and ends on the right

__<ins>Maze 1:</ins>__

![image](https://github.com/Muji90/SOFE-2715U-Final-Project/assets/145510715/fd64f08d-2f88-4def-8b48-3acbd55e6e49)

__<ins>Maze 2:</ins>__

![image](https://github.com/Muji90/SOFE-2715U-Final-Project/assets/145510715/e4a0e17a-b9f1-479d-b036-2743108e0431)

__<ins>Maze 3:</ins>__

![image](https://github.com/Muji90/SOFE-2715U-Final-Project/assets/145510715/e6d40a24-b6ab-4cbc-a355-193019a63b39)

As shown above the user has the ability to generate multiple mazes and has the ability to do as many as he/she desires


# <ins>Code</ins>

The Java code we made to build this project outline a maze game with visualization and functionalities for generating and solving mazes. It uses an n x n algorithm for maze generation and solving, and employs various data structures for its operation. Here's an overview of how it works:

__<ins>Maze Generation and Solving</ins>__

__- Maze Generation:__ The RandomMaze class generates mazes using Kruskal's algorithm, a minimum spanning tree algorithm. This algorithm works well for maze generation because it ensures there's a path between any two points in the maze without creating loops, which is ideal for mazes. The algorithm starts by treating each cell as a separate set (or tree in a forest of minimum spanning trees). Then, it randomly selects walls to remove, but only if the cells on either side of the wall are not already connected. This process continues until all cells are connected. The maze is initialized with walls in every cell (WallMaze method) and then carves out paths by removing walls (CreateNodes and KruskalTree methods).

__- Solving Algorithm:__ While the code snippets provided don't include a specific maze-solving algorithm implementation, they lay the groundwork for such an implementation. The maze solving could be done using algorithms like A*, Dijkstra's, or BFS (Breadth-First Search). These algorithms would navigate the maze from a start point to an end point, searching through possible paths and avoiding walls.

__<ins>Data structures used to build this project</ins>__

| Data Structures  | Description |
| ------------- | ------------- |
| 2D Array  | The maze itself is represented as a 2-dimensional array of integers (int[][] maze). This array holds information about the state of each cell in the maze, such as whether it's a wall, empty, the start point, the destination, or part of the path found by the algorithm  |
| ArrayLists  | In the RandomMaze class, an ArrayList of Edge objects is used to represent possible connections (paths) between cells in the maze. This list is crucial for implementing Kruskal's algorithm, as it allows for randomly selecting and removing walls to create a path  |
| Graph Data Structure  | The inner Graph class in the RandomMaze class represents a graph where nodes correspond to cells in the maze, and edges represent potential paths between these cells. This graph is used in the Kruskal's algorithm implementation to keep track of connected components and ensure the resulting maze is solvable  |
| Point Class  | The Point class is used to represent the coordinates (x, y) of cells in the maze. This class is pivotal for tracking the position of walls, paths, the start point, and the destination within the maze  |

# <ins>Visualization and Interaction</ins>

__- MazeVisualizer:__ This class extends JFrame and provides a graphical user interface (GUI) for the maze game. It includes buttons for generating and solving the maze, as well as for manual maze modification. It listens for mouse events to allow the user to interact with the maze, such as adding or removing walls.

__- HelpWindow:__ Another JFrame class providing instructions and help for users. It is a separate window that can be opened from the main application.

# <ins>Major breakdowns</ins>

__1. Define the maze size:__ The size of the maze is set with HEIGHT and WIDTH constants, which determine the number of cells and walls within the maze. In the Maze class, these dimensions are used to define the two-dimensional array representing the maze grid.

__2. Initialize the maze grid:__ A method, clearMaze(), initializes the maze grid with boundary walls (value 1) and empty spaces (value 0). The outermost cells are initialized to walls, and the inner cells are set to empty.

__3. Wall setup:__ The method WallMaze() is used to set all the cells in the maze as walls. This prepares the maze for the generation algorithm by starting with a grid of walls.

__4. Randomized wall removal for maze paths:__ RandomMaze class generates a maze by removing certain walls according to Kruskal's algorithm. This process effectively carves pathways into the full wall grid initialized by the previous step.

__5. Generate a minimum spanning tree:__ In the RandomMaze class, the Graph and its method KruskalTree represent and apply Kruskal's algorithm. It finds a minimum spanning tree by connecting nodes with edges without forming cycles, which translates to a solvable maze without loops.

__6. Create the maze:__ After the minimum spanning tree is generated, walls in the maze grid are removed where the edges of the tree indicate a path should be. This is done within the KruskalTree method, which changes values in the maze array from walls to paths.

__7. Set start and end points:__ The code snippets do not explicitly show methods for setting start and end points, but the RandomMaze class's setStartAndEndPoint method indicates where this would happen. Start (value 2) and finish (value 9) points can be placed in predefined or random locations.

__8. Visualization and interaction:__ The MazeVisualizer class handles the visualization and allows the user to interact with the maze. It includes methods for painting the maze on the screen and responds to user inputs such as mouse clicks for modifying the maze or triggering the generation and solving processes.
