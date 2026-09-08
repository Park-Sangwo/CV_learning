Sensing Color FPCV-1-2 2026/09/08

## 1. Camera Response Function (CRF)

Radiometric Calibration - mapping pixel brightness values back to actual scene irradiance (physical light energy)

Exposure Equation - total light energy exposure $e$ received by a pixel is $e = E \cdot t$ (Irradiance $E$ times Exposure Time $t$)

Camera Response Function $f$ - non-linear mapping function converting exposure $e$ to digital pixel intensity
$$I = f(e) = f(E \cdot t)$$

Reasons for Non-linearity:
Historical display gamma, human visual perception, and the need to compress a wide dynamic range into 8-bit values

Linearization - use $f^{-1}$ to convert pixel values back to relative scene radiance    
$$E = \frac{f^{-1}(I)}{t}$$


## 2. High Dynamic Range (HDR) Imaging Problem

real-world scenes often exceed 100,000:1 contrast ratios while LDR cameras are limited to 8-bit (256 levels)

Short exposure - dark areas may become too noisy or almost black

Long exposure - bright areas can become saturated at 255, so highlight information is lost

Therefore, we need to capture the full dynamic range of a scene without highlight clipping or shadow noise saturation


## 3. Multi-Exposure HDR Capture and Fusion

Multi-Exposure Bracketing - taking multiple photos of a static scene at varying exposure times ($t_1, t_2, \dots, t_k$)

(Short exposures capture bright highlights clearly, long exposures capture dark shadow details clearly)

HDR Fusion Algorithm:

Map pixel values of each exposure image to relative irradiance using $f^{-1}$:
$$E_k = \frac{f^{-1}(I_k)}{t_k}$$

Combine the irradiance estimates from different exposures using a weighted average:
$$E_{\text{final}} = \frac{\sum_{k} w(I_k) \cdot \frac{f^{-1}(I_k)}{t_k}}{\sum_{k} w(I_k)}$$

Weighting Function $w(I)$ - assigns higher weights to mid-tone pixel values (around 128) and near-zero weights to extreme values (0 or 255)

(Extreme values are discarded because 0 is dominated by read noise and 255 is saturated without true radiance information)


## 4. Tone Mapping

HDR Image Representation - output is stored as 32-bit floating point values representing absolute/relative radiance

Tone Mapping - process of compressing high dynamic range floating-point data into low dynamic range (8-bit) for standard displays

To reduce global contrast to fit display limits while preserving fine local details and visual features
