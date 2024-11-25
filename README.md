# UCD-SDP: Ultracool dwarfs spatial distribution and profile

UCD-SDP is a code that models the spatial distribution of ultracool dwarfs in the Galactic disk, aiming to measure the thin disk scale parameters of the L and T population. The code shows the applicability of the fitting method to a full sky sample of M ($\geq$ M9), L and T synthetic dwarfs from GalmodBD simulation (for more information, Galmod is described in [Carnero Rosell et al. 2019](https://ui.adsabs.harvard.edu/abs/2019MNRAS.489.5301C/abstract)).

## How it works

To fit the spatial number density profile we use a double exponential model for the Galactic thin disk:

``` math
n(\vec{r}) = n(0,0)e^{-R/R_{s}} e^{-|z|/z_{s}}
```

``` math
n(\vec{r}) = n(R_{\odot},0)e^{-(R-R_{\odot})/R_{s}} e^{-|z|/z_{s}}
```

where $R$ and $z$ are Galactocentric cylindrical coordinates, $R_s$ and $z_s$ are the scale length and height, respectively, $R_{\odot}=8$ kpc is the cylindrical radial coordinate of the Sun, also assumed to be at $z_{\odot}=0$, and $n(0,0)$ (or alternatively $n(R_{\odot},0)$ ) is the profile normalization. 

The fits are carried out using the Markov Chain Monte Carlo (MCMC) method to sample parameter space and find the best model based on the maximization of likelihood or $-\chi^2$. The method we adopted not only fits the scale parameters $R_{s}$ and $z_{s}$, but is also able to provide the density profile normalization.

## Important notes

- The GalmodBD simulations have $R_s$ = 2.5 kpc and $z_s$ = 250, 350 and 450 pc and a magnitude limit of z < 23. 
- To account for selection effects, we adopt volume-limit samples.
- The user can choose between likelihood and $\chi^2$ statistics to apply the MCMC method.
