# A-Search-for-Sliding-Puzzle
The program composed of the class puzzle, class search and a couple of global variables, including the goal state, alphabetical sequence values, the x-axis and y-axis. The program would first initialize with the initial state puzzle and set the goal state puzzle as the target, then perform a* search to find a path and list the visited tiles.
	goalState = ["0", "1", "2", "3", "4", "5", "6", "7", "8"] #values of puzzle
	abcdefghi = [["A", "B", "C"], ["D", "E", "F"], ["G", "H", "I"]] #predefined 2d array
	xAxis = [1, 0, -1, 0]
	yAxis = [0, 1, 0, -1] 
	n = 3 #number of column

# Class Puzzle
Puzzle is referring to the state of the game. It contains the node, reference to the parent node, value, tier, and heuristic score. It also includes some get/set function to return level, the state, and the heuristic score.

# Class Search
Search is the implementation of a* algorithm. It has the initial state and the goal state of the puzzle board, with a set of nodes and visited nodes. 

	def findPath(this):
It also has the find path function that defines the size of the search into a queue, then declares the root node and the supposed position of the empty label. While staying within scope of the search, move the node according to the value of f-score, the sum of the step visited nodes (g, the levels of puzzle) and the distance of goal node(h, the position of goal tile), and push to the list containing the new state for each iteration, expanding the path. It continues until the goal state is equal to the current state.

	def aStar(initState, goalState):
The function that applies findPath as well as getSeq to print the output

# Print Output
The position will be indicated by the x/y axis to determine the direction of the moved ‘0’, which then reverses from the queue and match the predefined 3x3 2d array of characters and output the alphabet.
        for node in reversed(path):
            currentIndex = node.getState().index(0) #value of the puzzle
            currentI, currentJ = currentIndex // goalState.shape[
                0], currentIndex % goalState.shape[0]
            output += getSeq(currentI, currentJ)
        print(output)


predefined 3x3 2d array:
def getSeq(n, m):
    return abcdefghi[n][m]

# Library used – numpy, queue
Some libraries specific functions have been used to complete the assignment, including queue to store the nodes = PriorityQueue(1000)
and array.flatten) to turn a 2d array to list temporarily so that it fits the parameter of class Puzzle, namely state and goalState. In addition, reshape(n,n) turn the array into n x n, which is 9 since n=3 as defined globally.	
Method learned from online source
	As I need to specifically compare the initial state and destinated state, the modified greater than/lower than/ equal to method is applied, referenced in python OOP tutorial.
https://www.pythontutorial.net/python-oop/python-__eq__/
