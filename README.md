# Background Information
*   Task: Make a universal code to find spectra for the number of photons emitted from an exoplanet at the feature wavelengths of certain biosignature gases by **querying data from the NASA Exoplanet Archive** and **using the blackbody radiation equation**.
*   Given Information
    *   Spectral radiance (blackbody radiation) equation in terms of wavelength
        *   $B_{λ} = \frac{2hc^2}{λ^5} \times \frac{1}{e^\frac{hc}{λkt}}$
        *   Units: $\frac{W}{m^3 \times sr}$
    *   Energy of a photon equation
        *   $E_{photon} = \frac{hc}{λ}$
        *   Units: $J$
    *   The scaling factor for the calculation          
        *   $A \times t \times (\frac{R_{star}}{d})^2$
            *   $A$ = telescope collecting area ($cm^2$)
            *   $t$ = exposure time ($s$)
            *   $R_{star}$ = radius of the star ($m$)
            *   $d$ = distance from the star to the detector ($m$)
            *   Units: $cm^2 \times s$

*   Use $B_{λ}$, $E_{photon}$, and $A \times t \times (\frac{R_{star}}{d})^2$ to find $N$, the number of photons emitted from an exoplanet at an interval of wavelengths.
    *   $N = \int_{λ}^{λ} (\frac{2c}{λ^4} \times \frac{1}{e^\frac{hc}{λkt}} \times A \times t \times (\frac{R_{star}}{d})^2)dλ$
*   Stellar radius, effecive temperature, and distance will be queried from the NASA Exoplanet Archive for the a selected exoplanet.
    *   We will also assume that $A =$ 7.0685 $\times 10^6 cm^2$ and $t =$ 100 $s$.
*   Each biosignature gas uses its own feature wavelength ($λ$) range. This is the interval of the integral.
    *   $O_2 =$ 1.25 - 1.28 $μm$
    *   $CO_2 =$ 4.17 - 4.51 $μm$
    *   $CH_4 =$ 3.41 - 3.71 $μm$
    *   $H_2O =$ 1.76 - 1.94 $μm$
*   From here, we can evaluate the number of photons emitted for each biosignature gas at a feature wavelength range from an exoplanet. We can use this information, along with our calculated minimum photon count for a certain small error on our Poisson distribution, to decide how long to collect data for ($t$, exposure time) or how wide our detector should be ($A$, telescope collecting area) for a given exoplanet.
