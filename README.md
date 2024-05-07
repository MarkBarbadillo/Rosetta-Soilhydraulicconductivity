## This repository enables you to generate soil  hydraulic parameters and predict unsaturated hydraulic conductivity (K) using the pedotransfer function 'Rosetta'
### Can do:
#### Estimation of hydraulic parameters (theta_s, theta_r, alpha, n, Ks) using percent sand, silt, and clay, bulk density [g/cm3], and volumetric water contents (vwc) [cm3/cm3] at -33 and -1500 kPa
#### Comparison between hydraulic conductivity values obtained from different versions of Rosetta (V.1, 2, 3)
#### Plotting of hydraulic conductivity values (V.1 versus V.3)
#### Predict K0 from Ks obtained from Rosetta Version 3

## Unsaturated hydraulic conductivity comparison: K0 + L + hydraulic parameters from Rosetta V.1 -- VERSUS --  Ks + L = 0.5 + hydraulic parameters from Rosetta V.3
#Plotting hydraulic conductivity values obtained from Rosetta versions 1 and 3
import matplotlib.pyplot as plt

fig = plt.figure(figsize=(8,5))
plt.xlabel('Hydraulic conductivity_Ros.V3 [cm/day]', fontsize=12, labelpad=8)
plt.ylabel('Hydraulic conductivity_Ros.V1 [cm/day]', fontsize=12, labelpad=8)
plt.tick_params(axis='both', which='major', labelsize=12,pad=8)
plt.tick_params(axis='both', which='minor', labelsize=12,pad=8)
plt.plot(K3, K1, 'ok')

## Steps in getting Hydraulic conductivity for unsaturated soils:
#### Estimate the hydraulic parameters
#### Obtain the matric potential values
#### Convert the matric potential values to vwc using the van Genuchten equation:s
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

$$
n = \text{retention shape parameter}
$$

$$
m = 1 - \frac{1} {n}
$$




![image](https://github.com/MarkBarbadillo/Rosetta-Soilhydraulicconductivity/assets/157748709/3b781a05-5abf-4ba0-9782-230f65226561)
