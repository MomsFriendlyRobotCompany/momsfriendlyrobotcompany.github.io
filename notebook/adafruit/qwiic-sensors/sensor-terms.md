## Terms

Power Spectral Density:

- Power: mean-squared value
- Spectral: distribution of a signal over a spectrum of frequency
- Density: mangitude of the PSD is normalized to a single Hz bandwidth

$$
RMS_{noise} = NoiseDensity \sqrt{BW * filter}
$$

where $bandwidth$ is half the Output Data Rate (ODR), $filter$ is a low pass filter having one of the following values:

- 1.57(1st order)
- 1.11 (2nd order)
- 1.05(3rd order)
