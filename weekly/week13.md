# Binary Images FPCV-1-3 2026/10/10

## 1. Segmentation and Connected Components

Need for Segmentation - when an image contains multiple objects, each object needs a unique label before its geometric properties can be calculated

Connected Component - a maximal set of connected points, Two points are connected if a path exists between them along which `b(x,y)` remains constant

Region Growing Algorithm - starts from an unlabeled seed point and expands to its connected neighbors:
1. Scan the image in raster order to find an unlabeled seed point with `b(x,y) = 1`
2. Assign a new label to the seed point
3. Assign the same label to adjacent neighbors with `b(x,y) = 1`. Continue expanding until no unlabeled neighbors remain
4. Repeat the scan to find the next unlabeled seed point


## 2. Neighborhood Connectedness and Topological Dilemma

4-Connectedness (4-C) - each pixel is connected to its four orthogonal neighbors (top, bottom, left, and right)

8-Connectedness (8-C) - each pixel is connected to all eight surrounding neighbors, including diagonals

Jordan's Curve Theorem - a closed curve divides the plane into two regions: inside and outside

4-C Problem - diagonal pixels are not connected, so the ring becomes four separate objects. The background is also split into two regions

8-C Problem - the four foreground pixels form one connected ring, but the inside and outside backgrounds remain connected through diagonal corners


## 3. Asymmetric 6-Connectedness and Hexagonal Tessellation

6-Connectedness (6-C) - introduces asymmetry by removing two diagonal neighbors from the 8-neighborhood

Topology Consistency - in this example, 6-C produces two separate line segments and one connected background, consistent with Jordan's Curve Theorem

Hexagonal Tessellation - this asymmetric neighborhood makes a square pixel grid behave like a hexagonal grid, where each pixel has six neighbors


## 4. Sequential Labeling Algorithm

Two-Pass Labeling - uses raster scanning and neighboring pixel labels to assign connected component labels

Local Neighborhood - for the current pixel A, check the already-labeled neighbors B (top), C (left), and D (top-left)

First Pass Labeling Rules:
- If `A = 0`, label A as background
- If `A = 1` and all three neighbors are 0, assign a new label
- If D is labeled, assign A the label of D
- If C is labeled and D = 0 and B = 0, assign A the label of C
- If B is labeled and D = 0 and C = 0, assign A the label of B
- If B and C have the same label, assign A that label

Equivalence Resolution:
- Label Conflict - occurs when D = 0 and B and C have different labels
- Equivalence Table - assign A the label of B and record that labels B and C are equivalent
- Second Pass - scan the image again and replace equivalent labels with a single label for each connected component
