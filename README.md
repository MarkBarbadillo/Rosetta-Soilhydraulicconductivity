## This repository enables you to generate soil  hydraulic parameters and predict unsaturated hydraulic conductivity (K) using the pedotransfer function 'Rosetta'
### Can do:
#### 1) Estimation of hydraulic parameters (theta_s, theta_r, alpha, n, Ks) using percent sand, silt, and clay, bulk density [g/cm3], and volumetric water contents (vwc) [cm3/cm3] at -33 and -1500 kPa
#### 2) Comparison between hydraulic conductivity values obtained from different versions of Rosetta (V.1, 2, 3)
#### 3) Plotting of hydraulic conductivity values (V.1 versus V.3)
#### 4) Predict K0 from Ks obtained from Rosetta Version 3

## Steps:

#### 1) Estimate the hydraulic parameters
#### 2) Obtain the matric potential values from 'longtermmeans.csv'
#### 3) Convert the matric potential values to vwc using the van Genuchten equation:
$$vwc = \theta_r + (\theta_s - \theta_r) [1 + (-\alpha * \psi_m)^{n}]^{-m}$$

Where:

$$\theta_r = \text{residual volumetric water content} [\frac{cm^3}{cm^3}]$$

$$\theta_s = \text{saturated volumetric water content} [\frac{cm^3}{cm^3}]$$

$$\alpha = \text{retention shape parameter} [\frac{1}{cm}]$$

$$\psi_m = \text{matric potential [kPa]}$$

$$n = \text{retention shape parameter}$$

$$m = 1 - \frac{1} {n}$$

#### 4) Calculate the effective saturation (Se):
$$S_e = \frac {vwc - \theta_r} {\theta_s - \theta_r}$$

#### 5) Calculate the unsaturated hydraulic conductivity [cm/day] using K0 + Rosetta V.1 parameters using the equation:
$$K(S_e) = K_0 * S_e^{L} * [1 - (1 - S_e^{\frac{n}{n-1}})^m]^2$$

Where:

$$L = \text{unitless emperical coefficient obtained from Rosetta V.1}$$

#### 6) Compare the K obtained using K0 + Rosetta V.1 parameters with the K obtained using Ks + L=0.5 + Rosetta V.3 parameters:
$$K(\theta) = K_s * S_e^{L} * [1 - (1 - S_e^{\frac{1}{m}})^m]^2$$

Where:

$$L = 0.5\ \text{(default value)}$$

#### 7) Plot the results:
##### Example: Plotting Ks from Rosetta V.3 versus K0

![image](https://github.com/MarkBarbadillo/Rosetta-Soilhydraulicconductivity/assets/157748709/67f6fb99-ba92-44b4-9654-7dce802612dd)


## References

#####[1] Wyatt, B.M., Ochsner, T.E., Fiebrich, C.A., Neel, C.R., Wallace, D.S. (2017). Useful drainage estimates obtained from a large-scale soil moisture monitoring network by applying the unit-gradient assumption. Vadose Zone Journal 16(6): 1-15. https://doi.org/10.2136/vzj2017.01.0016
#####[2]https://github.com/usda-ars-ussl/rosetta-soil
