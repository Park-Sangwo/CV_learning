Resolution, Noise, Dynamic Range FPCV-1-2 2026/07/09

## 1. Photon Shot Noise (Scene Dependent)

due to the quantum nature of light itself and the random arrival of photons

Bucket model - pixels collect photons over a fixed exposure time like buckets collecting raindrops

modeled using the Poisson distribution

$$P(\text{signal} = k) = \frac{\lambda^k e^{-\lambda}}{k!}$$

Property - variance of the distribution is equal to its mean ($\text{Var}[\text{signal}] = \text{Mean}[\text{signal}]$)

As brightness increases, the mean and variance increase, and the distribution begins to look Gaussian for $\lambda \ge 10$


## 2. Read Noise & Quantization Noise (Scene Independent)

Read Noise - introduced during the conversion of electrons to a voltage by the conversion circuit
(depends entirely on sensor quality and is independent of scene brightness)

Quantization Noise - introduced during analog-to-digital conversion (ADC) when converting voltage to discrete integer values
Variance of quantization noise - delta squared divided by 12 ($\text{Var} = \frac{\Delta^2}{12}$ where $\Delta$ is the quantization step)

quantization noise is negligible due to high intensity resolution (12-14 bits)


## 3. Other Noise Sources (Scene Independent)

Dark Current Noise (Thermal Noise) - electrons generated within the image sensor due to its temperature even without light
(Follows Poisson distribution; significant only for long exposures such as in astronomy applications)

Mitigation for thermal noise - cooling the image sensor to a specific given temperature

Fixed Pattern Noise - comes from manufacturing imprecisions where no two pixels have identical responses to light
Mitigation for fixed pattern noise - reduced by calibrating the gain of each pixel or using dark frame subtraction


## 4. Sensor Dynamic Range

Dynamic Range - the range of brightness values an imaging system is able to measure safely without saturation or noise hiding

$$\text{Dynamic Range} = 20 \log_{10} \left( \frac{B_{\text{max}}}{B_{\text{min}}} \right) \text{ decibels (dB)}$$

$B_{\text{max}}$ - the maximum possible photon energy the pixel can measure (full potential well capacity)

$B_{\text{min}}$ - the minimum detectable photon energy distinguishable in the presence of noise

* Human Eye - 1,000,000:1 ratio / ~120 dB
* Digital Still Camera - 4096:1 ratio / ~72.2 dB 
* Digital Video Camera: 45:1 ratio / ~33.1 dB
