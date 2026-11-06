Image Processing I FPCV-1-4 2026/11/06

## 1. Pixel Processing

Image Processing Objective - transform an image into one that is clearer, easier to analyze, or optimized for feature detection

Pixel (Point) Processing - simplest form of image processing transforming brightness or color of each pixel independently of its spatial location

$$g(x,y) = T(f(x,y))$$

where $f$ is input, $g$ is output, and $T$ is the mapping function

Common Point Operations - Darken / Lighten, Invert, Contrast Adjustment, Grayscale Conversion


## 2. Linear Shift Invariant System (LSIS)

LSIS - foundational framework for studying linear image processing algorithms

Linearity Property - a linear combination of inputs yields the exact same linear combination of corresponding outputs

$$\alpha f_1 + \beta f_2 \longrightarrow \text{LSIS} \longrightarrow \alpha g_1 + \beta g_2$$

Shift Invariance Property - shifting the input by $a$ results in an identical shift of $a$ in the output:

$$f(x-a) \longrightarrow g(x-a)$$


## 3. Convolution Principles

Convolution Definition - mathematical operation denoted by an asterisk (*), stating that any LSIS performs convolution and vice versa:

$$g(x) = f(x) * h(x) = \int_{-\infty}^{\infty} f(\tau)h(x-\tau)d\tau$$

Geometrical Visualization Steps:

1. Flip the filter function $h(\tau)$ about the vertical axis to obtain $h(-\tau)$
2. Shift the flipped filter by $x$ to get $h(x-\tau)$
3. Multiply the overlapping functions and integrate over all space from minus to plus infinity as $x$ slides

Properties of Convolution:
* Commutative - $a * b = b * a$
* Associative - $(a * b) * c = a * (b * c)$
* Cascaded Systems - sequential convolutions can be merged into a single equivalent convolution filter

2D Convolution Extension - applied to 2D image signals $f(x,y)$ with a 2D kernel $h(x,y)$ where spatial variables are flipped in both dimensions:

$$g(x,y) = \iint_{-\infty}^{\infty} f(\tau, \mu)h(x-\tau, y-\mu)d\tau d\mu$$


## 4. Unit Impulse Function and Impulse Response

Unit Impulse Function (Delta Function $\delta(x)$) - infinitesimally thin, infinitely tall function with a total area equal to 1

Sifting Property - convolving any function $b(x)$ with a unit impulse extracts the function itself:

$$\int_{-\infty}^{\infty} \delta(\tau)b(x-\tau)d\tau = b(x)$$

Impulse Response ($h$) - the output produced when a unit impulse function is fed into an unknown LSIS black box; fully describes the system

Point Spread Function (PSF) - the impulse response of an optical imaging system 
ex) human eye responding to a distant star point source $\delta(x,y)$
