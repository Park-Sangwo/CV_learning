Image Formation FPCV-1-1, Image Formation using Lenses 2025/05/13

## 1. Gaussian Lens (Thin Lens) Law
Unlike a pinhole, the center of a lens functions as a pinhole. 
It converges light rays spreading in multiple directions into a single point.

Assuming the thickness of the lens is negligible compared to its focal length (thin lens approximation), 
the relationship between the object distance ($d_o$), image distance ($d_i$), and focal length ($f$) is as follows:

$$\frac{1}{o} + \frac{1}{i} = \frac{1}{f}$$

In the case of magnification(using the properties of similar triangles),

$$M = \frac{h_i}{h_o} = \frac{i}{o}$$

## 2. Zooming, two lens system
One can change the magnification of a lens camera by using multiple lenses.
Without changing the distance between the object and the image plane, 
the magnification of the entire system can be varied by shifting the positions of the two lenses. 
This process is referred to as “zooming.”

$$M = \frac{i_2}{o_2} = \frac{i_1}{o_1}$$

## 3. Aperture of Lens
The aperture of the lens is the clear area of the lens that gathers light from points in the scene. 
The ratio of the focal length to the diameter of the aperture is called the f-number.

Aperture - $$D = \frac{f}{N}$$

f-Number - $$N = \frac{f}{D}$$

ex) A 5066 focal length, f/1.8 lens implies:
N = 1.8 (D = 27.78mm) when aperture is fully open

## 4. Lens Defocus
The plane of focus - There is only one plane in the scene that is perfectly focused onto the image plane by a lens.

Since it is closer to the lens than the focused point o, its image will be formed behind the image plane.
The light will not correspond to a single point on the image plane, but instead it will be distributed over a circular disk.
-> blur circle

(blur circle diameter - $b$)

$$\frac{b}{D} = \frac{|i' - i|}{i'}$$

Using Gaussian lens law 

$$i' - i = \frac{o'f}{o'-f} - \frac{of}{o-f}$$

$$b = \frac{f^2}{N} \cdot \frac{o - o'}{o'(o - f)}$$

$b \propto f^2$, if focus length increases, b increases

$b \propto \frac{1}{N}$, if f-number increases(aperture decreases), b decreases

$b \propto |o - o'|$, if the object moves further away from the original focal plane $o$ to $o'$, b increases

So, to bring the object into focus, we can move the image plane away from the lens, 
move the lens itself, or move both the lens and the image plane.
