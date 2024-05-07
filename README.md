## This repository enables you to generate soil  hydraulic parameters and predict unsaturated hydraulic conductivity (K) using the pedotransfer function 'Rosetta'
### Can do:
#### Estimation of hydraulic parameters (theta_s, theta_r, alpha, n, Ks) using percent sand, silt, and clay, bulk density [g/cm3], and volumetric water contents (vwc) [cm3/cm3] at -33 and -1500 kPa
#### Comparison between hydraulic conductivity values obtained from different versions of Rosetta (V.1, 2, 3)
#### Plotting of hydraulic conductivity values (V.1 versus V.3)
#### Predict K0 from Ks obtained from Rosetta Version 3

## Steps in getting hydraulic conductivity for unsaturated soils:

#### Estimate the hydraulic parameters
#### Obtain the matric potential values from '/content/drive/MyDrive/MABarbadillo/SPTProject/Rosetta/longtermmeans.csv'
#### Convert the matric potential values to vwc using the van Genuchten equation:
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

#### Calculate the effective saturation (Se):
$$S_e = \frac {vwc - \theta_r} {\theta_s - \theta_r}$$

#### Calculate the unsaturated hydraulic conductivity using K0 + Rosetta V.1 parameters using Mualem-van Genuchten Equation:
$$K = K_0 * S_e^L * (1-(1-S_e^{\frac{n}{n-1}}^m))^2$$



![image](https://github.com/MarkBarbadillo/Rosetta-Soilhydraulicconductivity/assets/157748709/3b781a05-5abf-4ba0-9782-230f65226561)
