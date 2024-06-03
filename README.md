# VisuAlgo
A web-based visualizer for Algorithms

### Overview

A web-based Visualizer for implementing and realizing:
1) Jarvis March and Kirk-Patrick Seidel Algorithms which constructs a Convex Hull given a set of two dimensional Points.
2) RNA folding algorithm which predicts the secondary structure of a given RNA sequence that dictates its physical and chemical properties.

**Kirk-Patrick Seidel Algorithm:**

The Kirkpatrick-Seidel algorithm, also known as the "Ultimate Planar Convex Hull Algorithm," is an efficient method for finding the convex hull of a set of points in the plane. The convex hull is the smallest convex polygon that can enclose a set of points, analogous to the shape formed by a tightened rubber band around the points. The Kirkpatrick-Seidel algorithm operates in \(O(n \log h)\) time, where \(n\) is the number of input points and \(h\) is the number of points on the convex hull. It uses a divide-and-conquer strategy to recursively split the problem into smaller subproblems, solve each subproblem, and then merge the results to form the final convex hull. This algorithm is notable for its optimal performance and sophisticated use of geometric properties to achieve high efficiency.

1) Initialization:Start by identifying the points with the minimum and maximum x-coordinates, denoted as p_min and p_max. These points are guaranteed to be part of the convex hull.

2) Divide : Find the median x-coordinate of the points to divide the set into two subsets. These subsets are separated by a vertical line L at the median x-coordinate.

3) Upper Bridge: Define the upper bridge, which is a segment connecting a point in the left subset to a point in the right subset. This segment is part of the convex hull's upper boundary.

4) Supporting Line and Slope Analysis: Determine the slopes of lines defined by pairs of points. This step incorporates Lemma 1 to eliminate any point below another with the same x-coordinate and Lemma 2 to consider the slope relative to the potential upper bridge.

5) Median Slope and Candidate Points: Find the median of the slopes of the lines determined from the pairs of points. Select candidate points for the next iteration based on their slope relative to the median slope.

6) Subset Partitioning: Partition the points into three groups based on their slope relative to the median slope: SMALL (less than the median), EQUAL (equal to the median), and LARGE (greater than the median).

7) Supporting Line Selection: For each subset, find a supporting line with the slope equal to the median slope and determine the points that lie on this supporting line. Use Lemma 3 to infer the positioning of the points relative to the median vertical line.

8) Bridge Determination: Establish whether the supporting line contains the bridge by comparing the x-coordinates of points with maximum y-value minus the slope times the x-coordinate.

9) Candidates Update: Update candidate points based on the location relative to the median line using the corollary derived from Lemma 2 and Lemma 3. Points on the wrong side of the median slope are not potential bridge points

10) Recursive Upper Bridge Construction: Recursively call the function to find the upper bridge with the updated candidates until the bridge is found or only two points remain, in which case these points form the upper bridge.

11) Upper Hull Construction: Combine the upper bridges found through recursion to construct the upper hull. Apply a similar process to construct the lower hull.

12) Merge: Merge the upper and lower hulls to form the complete convex hull of the set of points.

**Jarvis March Algorithm:**

The Jarvis March algorithm, also known as the Gift Wrapping algorithm, is a straightforward method for finding the convex hull of a set of points in the plane. It operates by "wrapping" around the set of points to form the convex hull. Starting from the leftmost point, the algorithm selects the point that is the most counterclockwise relative to the current point, iteratively adding these points to the convex hull until it returns to the starting point. This process effectively "wraps" the points to form the smallest convex polygon enclosing all the points. The Jarvis March algorithm has a time complexity of \(O(nh)\), where \(n\) is the number of input points and \(h\) is the number of points on the convex hull. While simple to implement, it is not as efficient as other algorithms like Graham's scan or the Kirkpatrick-Seidel algorithm for larger datasets.

**RNA Folding:**

An RNA folding algorithm is a computational method used to predict the secondary structure of an RNA molecule based on its nucleotide sequence. The primary goal is to determine the most likely way the RNA strand will fold back on itself to form stable base pairs (e.g., A-U and G-C pairs), which are crucial for its function.
The computational approach to predicting RNA secondary structure involves creating a dynamic programming algorithm to determine the most stable configuration under given constraints. The key to this algorithm is defining the optimal structure (OPT) for a given RNA segment. By breaking down the problem into smaller sub-problems, we can efficiently calculate the maximum number of stable base pairs for each RNA segment.

Dynamic Programming Approach: We use a recurrence relation where the OPT for a segment ending at base j is calculated based on whether j pairs with any preceding base t, separated by at least four bases to prevent sharp turns, as per biological constraints.
Optimal Substructure and Overlapping Subproblems: The solution leverages the fact that the best way to fold a segment of RNA can be derived from the best ways to fold its sub-segments, which are themselves smaller instances of the same problem. This approach ensures that each subproblem is solved only once, storing the results to avoid redundant calculations.
No Overlapping Pairs and Knots: The algorithm ensures that if two base pairs are included in the solution, they do not intersect or overlap, aligning with biological observations that RNA structures are generally knot-free.
By systematically expanding from the simplest subproblems to more complex ones, and by using efficient data structures to store intermediate results, this dynamic programming algorithm provides a powerful tool to predict RNA secondary structure, thus opening doors to deeper biological insights and applications in drug design.

## Getting Started

### Prerequisites

- Web Browser

### Compilation and Execution

1. **Clone the Repository:**
   ```sh
   git clone https://github.com/HarshAgg256/VisuAlgo
   cd VisuAlgo
   ```

2. **Algorithm - 1:**
   - Navigate to the `VisuAlgo` directory.
   - Click on the `main.html` to view the visualizer for Kirk Patrick and Jarvis March Algorithm on a web browser.

3. **Algorithm - 2:**
   - Navigate to the `VisuAlgo` directory.
   - Click on the `main.html` to view the visualizer for RNA Folding Algorithm on a web browser.



