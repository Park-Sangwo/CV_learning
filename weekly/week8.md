Image Sensing FPCV-1-2 2026/07/02

## 1. Converting Light into Electric Charge

Most image sensors in use today - are made of silicon, well-suited for converting optical images to digital numbers

When hit with a photon of sufficient energy, it releases an electron.

So, just need a method for converting electrons into voltage.


## 2. Image Sensor Pixel Size & Resolution

18-Megapixel Image Sensor - each pixel is roughly 1.25 micrometers along each of its two dimensions

Image resolution does not follow Moore's law

Resolution Limit - once pixel size is as small as the wavelength of light (approx 0.5um), shrinking it further does not increase true resolution


## 3. CCD - Charge Coupled Device

photon to electron conversion happens within the potential well of each pixel

Readout process - utilizes a circuit that enables each row to pass its collected electrons to the next row

Bucket brigade technique - electric fields are applied underneath the potential wells to shift electrons row by row

Final process - bottom row shifts electrons horizontally to the last pixel, converted to analog voltage, then digital output via ADC

Cons - highly sophisticated and complex technology needed to avoid losing electrons or collecting unwanted ones during transfer


## 4. CMOS - Complementary Metal-Oxide Semiconductor

each pixel includes its own circuit to convert electrons to voltage directly within the pixel

Pros - highly flexible; can read out just a small specific region of pixels at a much faster rate

Cons - each pixel has a smaller light sensitive area because of the electron-to-voltage conversion circuit sitting next to it

more commonly found in consumer cameras because of their flexibility and cost advantages


## 5. Sensing Color and Microlenses

A pixel has no way of determining color itself; it can only convert photons to electrons (grayscale)

Color Filters - situated above the pixels (typically RGB in a 2D Bayer Pattern)

Demosaicing - process of interpolating neighboring color values from a mosaiced raw image to obtain a full R, G, B measurement at each pixel

Microlens - a tiny lens sitting on top of each pixel to focus incoming light onto the smaller light sensitive area
(= funnels all light down to the photodiode)
(distance between the top of the microlens and the bottom of the circuitry is only about 9.6 micrometers)

Future Trend - integrating additional layers of circuitry beneath the image sensor to perform visual processing before the image is outputted
