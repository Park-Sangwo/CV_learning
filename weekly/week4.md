Image Formation FPCV-1-1, Image Formation using Lenses 2025/05/20

## 1. Depth of Field (DoF)
The depth of field is the entire range of scene depths within which objects appear acceptably sharp in the captured image.

A blurred image of a point is considered to be "acceptably sharp" if the diameter of its circle of confusion $c$ is less than or equal to a maximum permissible limit, which is typically determined by the pixel size of the sensor.


If $$o_1, o_2 $$ are the nearest and farthest distances respectively for which blur circle is maximum c,
(using expression for the blur circle diameter)

$$c = \frac{f^2 (o - o_1)}{N o_1(o - f)}$$

$$c = \frac{f^2 (o_2 - o)}{N o_2(o - f)}$$

$$o_2 - o_1 = \frac{2 o f^2 c N (o - f)}{f^4 - c^2 N^2 (o - f)^2}$$


## 2. hyperfocal distance

It is the closest distance a lens needs to be focused at such that all points beyond that distance will be in focus (that is, within the depth of field of the camera)

$$h = \frac{f^2}{Nc} + f$$

($f$ is the focal length, $N$ is the f-number, and $c$ is the maximum permissible blur circle diameter)

If an imaging system is designed to be focused on the hyperfocal distance, then we know that all points beyond h are going to be in focus.


## 3. trade-off between the DoF and the brightness of the image

Large Aperture (Small f-Number) - bright image or short exposure time, shallow DoF

Small Aperture (Large f-Number) - dark image or long exposure time, large depth of field


