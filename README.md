## This repository enables you to generate soil  hydraulic parameters and predict unsaturated hydraulic conductivity using the pedotransfer function 'Rosetta'

### Data requirement for Rosetta function

Percent sand, silt, and clay, bulk density [g/cm3], and volumetric water contents [cm3/cm3] at -33 and -1500 kPa


## Soil volumetric water content (vwc) is calculated from the matric potential values using the van Genuchten equation:

$$vwc = \theta_r + (\theta_s - \theta_r) [1 + (-\alpha * \psi_m)^{n}]^{-m}$$

Where:

$$
\theta_r = \text{residual volumetric water content} [\frac{cm^3}{cm^3}]
$$

$$
\theta_s = \text{saturated volumetric water content} [\frac{cm^3}{cm^3}]
$$

$$
\alpha = \text{retention shape parameter} [\frac{1}{cm}]
$$

$$
\psi_m = \text{matric potential [kPa]}
$$


This also compares the hydraulic parameters (theta_s, theta_r, alpha, n, Ks) and hydraulic conductivity for unsaturated soils using Rosetta Versions 1 and 3


![image](https://github.com/MarkBarbadillo/Rosetta-Soilhydraulicconductivity/assets/157748709/3b781a05-5abf-4ba0-9782-230f65226561)
