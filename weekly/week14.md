Binary Images FPCV-1-3 2026/10/10

## 1. Iterative Modification and Euler Number

Iterative Modification - repeatedly changing pixel values based on their neighboring pixels while preserving the object's structure
A method that gradually updates pixel values based on their neighboring pixels while aiming to preserve topological features, such as object connectivity and the number of holes

Euler Number ($E$) - number of bodies ($B$) minus number of holes ($H$):
$$E = B - H$$

Ex)
* Letter 'B': $1 \text{ Body} - 2 \text{ Holes} \implies E_b = -1$
* Letter 'i': $2 \text{ Bodies} - 0 \text{ Holes} \implies E_i = 2$
* Letter 'n': $1 \text{ Body} - 0 \text{ Holes} \implies E_n = 1$

Additivity Property - total image Euler number $E_{\text{image}}$ equals the sum of Euler numbers of non-overlapping sub-regions

($E_{\text{image}} = \sum E_{\text{region}}$)


## 2. Euler Differential and Neighborhood Classification

Euler Differential ($E^*$) - change in Euler number when center pixel transitions from 0 to 1:

$$E^* = E_{\text{after}} - E_{\text{before}}$$

Hexagonal Grid Neighborhoods - $2^6 = 64$ possible neighbor patterns categorized into 4 distinct classes based on $E^*$:
* $N_{+1}$ ($E^* = +1$): creates a new isolated body
* $N_{0}$ ($E^* = 0$): conservative neighborhood set where changing the center pixel does not change the Euler number
* $N_{-1}$ ($E^* = -1$): merges two bodies into one (reduces body count by 1)
* $N_{-2}$ ($E^* = -2$): merges three bodies into one


## 3. Conservative Operators and 16 Modification Algorithms

Conservative Operations - modifying pixels in N₀ neighborhoods keeps the Euler number unchanged

Parallelization - pixels that are not neighbors of each other can be modified simultaneously

Algorithm Derivation - specified set $S$ (e.g., $S \in N_0$), local condition $a_{ij}$ (1 if neighborhood $\in S$ else 0), and current bit $b_{ij}$:
* Input pair: $(a_{ij}, b_{ij}) \in \{(0,0), (0,1), (1,0), (1,1)\}$
* $2^4 = 16$ distinct binary output mapping functions (Algorithms 0 ~ 15)

Example of practical algorithms:
* Growing Objects (Dilation): set $S \in N_0$ and Algorithm 7 (changes $0 \to 1$ when $a_{ij}=1$)
* Thinning Objects (Skeletonization): set $S \in N_0$ and Algorithm 4 (changes $1 \to 0$ when $a_{ij}=1$)


## 4. Skeleton Extraction

Skeletonization - repeatedly apply Algorithm 4 with S = N₀ until no more pixels can be removed

Topological Preservation(Skeleton) - thins the object to obtain a skeleton while keeping the Euler number unchanged
