Image Sensing FPCV-1-2 2026/07/16

## 1. Quantum Efficiency and Silicon Properties

Quantum Efficiency $q(\lambda)$ - the ratio of the generated electron flux to the incoming photon flux of wavelength $\lambda$

Pixel Intensity $I$ - the total electron flux converted from the spectral distribution $p(\lambda)$ of incoming light

$$I = \int_{0}^{\infty} q(\lambda)p(\lambda)d\lambda$$

reaches $q(\lambda) = 1.0$ around 1000 nm wavelength where every photon converts to an electron

Silicon limits - virtually transparent for wavelengths above 1100 nm, and nearly opaque below 400 nm

Given only $I$ and $q(\lambda)$, it is impossible to uniquely find or recover the original $p(\lambda)$
(To measure specific values of $p(\lambda)$, specialized color filters must be placed in front of the pixels)


## 2. Human Visual System and Color Perception

Color - not a physical quantity, but rather the human response to different wavelengths of light

Retina structure - curved image sensor in the human eye utilizing two types of neurochemical pixels: rods and cones

light travels from the top and passes through ganglion and bipolar cells before reaching rods and cones

Rods - contain Rhodopsin; sense only brightness (not color) and operate in dark environments (scotopic vision)

Cones - contain Photopsin; discern color when there is enough light (photopic vision)


## 3. Cone Distribution and Resolution

Three types of cones - categorized into red, green, and blue sensors based on their spectral responses

Fovea - region of maximum visual acuity where cones are most dense and very few rods exist

Blind spot - a patch on the retina devoid of rods and cones where the optic nerve transmits images to the brain

(The human brain automatically fills in the missing visual information in the blind spot to create a continuous image)


## 4. Tristimulus Values and Metamers

Tristimulus curves - the specific quantum efficiency functions of the three types of cones: $h_r(\lambda), h_g(\lambda), h_b(\lambda)$

Tristimulus values (R, G, B) - the three specific intensity numbers produced by integrating the incoming spectrum

Metamers - a class of distinctly different spectral distributions $p(\lambda)$ that produce the exact same (R, G, B) values

Because of metamers, entirely different light spectra are perceived by humans as the exact same color

## 5. Engineering Approaches to Sensing Color

Dichroic Prism Approach - utilizes sophisticated optics to physically split an image into red, green, and blue components
ex) 3-CCD Camera
Cons of prism - the entire imaging system tends to be bulky and requires precise mechanical alignment

Color Filter Mosaic Approach - utilizes a single image sensor where each individual pixel has one color filter in front of it

Bayer Pattern - a popular color filter mosaic layout distributing filters over the pixel grid

Raw image - the initial mosaiced image outputted by the sensor where each pixel only measures one single color

Demosaicing - the software process of interpolating neighboring color values to fill in and recover full full-color images
