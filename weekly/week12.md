Binary Images FPCV-1-3 2026/09/22

## 1. Binary Images and Thresholding

Binary Image - image with only two intensity values (0 or 1), representing background (0) and object (1)

Thresholding - converting a gray-level image $g(x,y)$ to binary image $b(x,y)$ using threshold $T$:

$$\begin{cases} 0 & \text{if } g(x,y) < T ,\\ 1 & \text{if } g(x,y) \ge T \end{cases}$$

Threshold Selection via Histogram - analyzing brightness histogram to identify bi-modal distribution; choosing $T$ at the valley between background and foreground peaks

Capturing Binary Images - backlighting technique uses a translucent surface illuminated from beneath to eliminate shadows, shading, and surface textures


## 2. Geometric Properties of Continuous Binary Images

Area (Zeroth Moment) - gives the total size of the object; invariant to translation and rotation:

$$A = \iint_{I} b(x,y) \, dx \, dy$$

Position (First Moment) - centroid $(\bar{x}, \bar{y})$, which gives the center of the object:

$$\bar{x} = \frac{1}{A} \iint_{I} x \, b(x,y) \, dx \, dy, \quad \bar{y} = \frac{1}{A} \iint_{I} y \, b(x,y) \, dx \, dy$$

Orientation & Axis of Least Second Moment - axis that gives the smallest second moment

$$E = \iint_{I} r^2 \, b(x,y) \, dx \, dy$$

The axis of least second moment passes through the centroid and represents the object's main direction

Centroid-Centered Coordinate Shift - shift the origin to the centroid to simplify the calculation of the second moment

Minimizing $E$ & Orientation Angle - solving $\frac{dE}{d\theta} = 0$ yields:

$$\tan 2\theta = \frac{b}{a - c}$$

Roundedness Measure - ratio of minimum to maximum second moment $E_{\min} / E_{\max}$ (equals 1 for perfect circle/disk)

Grayscale Image → Binary Image → Area(size) → Centroid(position) → Second Moment(orientation and shape)

To simplify an image and describe an object using its size, position, orientation, and roundness

## 3. Discrete Binary Images and Real-Time Read-Out

Discrete Moment Formulas - use summations instead of integrals for area, position, and second moments:

$$A = \sum_i \sum_j b_{ij}, \quad\bar{x} = \frac{1}{A} \sum_i \sum_j i b_{ij}, \quad\bar{y} = \frac{1}{A} \sum_i \sum_j j b_{ij}$$

Origin-Based Second Moments - accumulating $a' = \sum \sum i^2 b_{ij}$, $b' = 2 \sum \sum ij b_{ij}$, $c' = \sum \sum j^2 b_{ij}$ relative to image origin

One-Pass Read-Out Efficiency - $A$, $\bar{x}$, $\bar{y}$, $a'$, $b'$, and $c'$ can be updated while the image is being read, then converted to the central moments $a$, $b$, and $c$ after the read-out


## 4. Segmenting Binary Images and Connectedness

Connected Component - a group of points connected by continuous paths with the same binary value

Connectedness & Jordan's Curve Theorem - 4-Connectedness (4-C) and 8-Connectedness (8-C) on square grids can cause problems with Jordan's Curve Theorem

6-Connectedness Solution - introducing diagonal asymmetry creates 6-Connectedness (6-C), which is similar to using a hexagonal grid

Sequential Labeling Algorithm - two-pass raster scan algorithm:

1. scan the image in raster order and check previously labeled neighbors ($B, C, D$) to label the current pixel $A$; record different labels that belong to the same object in an Equivalence Table
2. resolve the equivalences and give each connected component a single label
