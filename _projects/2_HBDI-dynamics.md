---
layout: project_page
title: HBDI Molecule Dynamics
description: I used with spectroscopy data to understand how fluorescent molecules move on the femtosecond timescale. 
img: /assets/img/HBDI.png
importance: 2
---

At the Fang Lab at Oregon State University, I delved into how these fluorescent proteins behave, and how we could make alterations that would improve them. 

## Introduction
HBDI is small modlecule that is the model chromohore for GFP. This molecule is essentially the fluorescent part of GFP. When this molecule is not inside the protein, it is not fluorescent because it is missing the protein environment, and instead proceeds through a different reaction pathway. We studied why this molecule does not behave the same in solution, and what alternative pathways it takes when exposed to light using a technique called femtosecond-stimulated Raman spectroscopy. This technique can the reveal ultrafast molecular motions at the moment a molecule is struck with a photon. One of the challenges with this technique is processing the large amount of data to the point when it can be interpreted, which was the focus in the project.

## Frequency Analysis 
A typical processed FSRS spectrum looks like this.
<img class="img-responsive dimmed-img mx-auto d-block" style="width: 90%;" src="{{ '/assets/img/HBDI-combined-stackplots.svg' | absolute_url }}" alt="HBDI FSRS plot">

The techique captures the Raman spectrum at several time deltas from the start of the photoexcitation process, allowing us to see how the reaction proceeds. In this spectrum, there are also oscillations modulating the spectrum, finding and characterizing them was my major focus in the project. These oscillations are interesting because they provide valuable information about how low-frequency vibrational modes interact with other modes, which we will see are important to understanding how the reaction happens. These can only be seen after removing the exponential time decay components from the spectrum.

One approach would be to take a single peak and for each time point, fit a model curve to it. The difference between the fitted model and the data would contain the oscillations that we are looking for. A drawback to this approach is that is time-consuming and has to be repeated for every peak of interest. I set out to create an approach that would reveal these oscillations for the entire spectrum in one go and reduce the amount of curve fitting that needed to be done.

To accomplish this I relied on a technique called Global Analysis, which models the spectrum as a series of separable non-linear models. This technique commonly used for other types of spectroscopy such as transient absorption spectroscopy but had not been applied to FSRS data due to its complexity. With several inputs to Glotaran, the GUI interface to create these models, a coarse model of the spectrum can be constructed. While the parameters from this type of model are not accurate enough to understand the system's time dynamics, the residuals from this model are good to analyze for oscillations. A Fourier transform of the residuals revealed key oscillations at the 866 cm<sup>-1</sup> mode, which was also confirmed by the traditional method.

<img class="img-responsive dimmed-img mx-auto d-block" style="width: 90%;" src="{{ '/assets/img/HBDI-fft-and-wavelet.svg' | absolute_url }}" alt="HBDI 2D FSRS and wavelet transform">


What does this all mean? The 226 cm<sup>-1</sup> frequency corresponds to a whole-molecule twisting motion, and we found evidence that it was happening during the chemical reaction. Without this frequency analysis, this mode would not have been seen because the Raman spectrum does not capture freuencies at this range.
This technique is referred to as 2D-FSRS in the paper. 


## Wavelet Transform
Going even further, I introduced the wavelet transform as a method to gain even more insights from these oscillations. A wavelet transform essentially provides a breakdown of the frequencies that are present at each point in time. Here is what a wavelet of the 866 <sup>-1</sup> mode.

As you can see, the wavelet transform shows that the 226 <sup>-1</sup> mode that is dominant in the frequency spectrum emerges at a delay 0.5 ps after photoexcitation and reaches a maximum at around 0.9 ps. This insight supports the previous hypothesis that there is an intermediate state in this reaction, something that was also corroborated by other evidence from this study. 

## Conclusion

<img class="img-responsive dimmed-img mx-auto d-block" style="width: 60%;" src="{{ '/assets/img/HBDI-vibration.png' | absolute_url }}" alt="HBDI twisting vibration">

In conclusion, 2D-FSRS and wavelet transform techniques provided important evidence that revealed an important oscillation that corresponded to an important twisting motion. Subsequent wavelet transform of the data revealed that this mode appears after a 0.5 ps delay from the beginning of the reaction, which supported the hypothesis that the molecule proceeded through an intermediate state. The technique that I developed in this study can be applied to study other systems. Check out the **link goes here*** project page for more details about the pipeline and an interactive web application.

<div class="center-block text-center">
  <a class="btn btn-sm" role="button" href="{{ '/assets/pdf/Physcon-HBDI.pdf' | absolute_url }}">HBDI Poster</a>
</div>