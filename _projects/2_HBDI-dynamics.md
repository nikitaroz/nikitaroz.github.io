---
layout: project_page
title: HBDI Molecule Dynamics
description: I used with spectroscopy data to understand the photochemistry of a small molecule.
img: /assets/img/HBDI.png
importance: 2
---

## Introduction
HBDI is small molecule that is the model chromophore of the Green Fluorescent Protein (GFP); in other words, it is fragment responsible for fluorescence in GFP. When this molecule is not inside the protein, it is not fluorescent because it is missing the protein environment. I studied what alternative pathways this molecule takes instead when exposed to light. I relied on a technique called femtosecond stimulated Raman spectroscopy (FSRS), a technique that can the reveal the ultrafast molecular motions at the moment a molecule is struck with a photon. One of the challenges with this technique is processing the large amount of data to the point when it can be interpreted, which was the focus in the project.

## Frequency Analysis 
FSRS captures the Raman spectrum at several time deltas from the start of the photoexcitation process, allowing us to see how the reaction proceeds. One of the first challenges are the large, non-linear baselines that are present in this data. The figure below shows the spectrum before and after baselines are removed.

<img class="img-responsive dimmed-img mx-auto d-block" style="width: 90%; background: white;" src="{{ '/assets/img/HBDI-combined-stackplots.svg' | absolute_url }}" alt="HBDI FSRS plot">

 In this spectrum, there are also oscillations modulating the spectrum, finding and characterizing them was my major focus in the project. These oscillations are interesting because they provide valuable information about how low-frequency vibrational modes interact with other modes, which are important to understanding the photochemical reaction.

To see these oscillations, the exponential time-dynamics of each of the peaks needs to be removed.
One approach is to fit one or several "bell curves" to each peak of interest. The difference between the fitted model and the signal would contain the oscillations. This approach, however, has the drawback of being time-consuming and that its scope is limited to the chosen peaks. I set out to create an approach that would simultaneously be faster and reveal oscillations for the entire spectrum in one pass.

I relied on a technique called Global Analysis, which models the spectrum as a series of separable non-linear models. It is commonly used for other types of spectroscopy such as transient absorption spectroscopy, but had not been applied to FSRS data because its spectra a typically too complex to accurately model with Global Analysis. The model, however, can produce a reasonable estimate of a spectrum's exponential time-dynamics, even if its fitted parameters are less meaningful. I used Glotaran, the GUI interface to create Global Analysis models, to generate an approximate model for the spectrum. A Fourier transform of the residuals revealed key oscillations at the 867 cm<sup>-1</sup> mode (figure to the left), which was also confirmed by the traditional method.

<img class="img-responsive dimmed-img mx-auto d-block" style="width: 90%; background: white;" src="{{ '/assets/img/HBDI-fft-and-wavelet.svg' | absolute_url }}" alt="HBDI Fourier and wavelet transforms">

The 232 cm<sup>-1</sup> frequency that is visible in the Fourier transform corresponds to a whole-molecule twisting motion. This is evidence that this motion is happening during the chemical reaction. Without a Fourier analysis of the spectrum, this mode would not have been seen because the Raman spectrum does not capture freuencies at this range.

## Wavelet Transform
Going even further, I introduced the wavelet transform as a method to gain more insight into these oscillations from the residuals. A wavelet transform provides a breakdown of the frequencies that are present as a function of time. The transform of the 867 cm<sup>-1</sup> mode is shown in the right figure above. It shows that the 232 cm<sup>-1</sup> mode emerges at a delay 0.5 ps after photoexcitation and reaches a maximum at around 0.9 ps. This insight supports the hypothesis that there is an intermediate state in the photochemical reaction, something that is corroborated by other evidence from the study. 

## Conclusion
In conclusion, the Fourier transform provided important evidence that revealed an important oscillation that corresponded to an important twisting motion that is shown below.

<img class="img-responsive dimmed-img mx-auto d-block" style="width: 60%;" src="{{ '/assets/img/HBDI-vibration.png' | absolute_url }}" alt="HBDI twisting vibration">

The subsequent wavelet transform of the 867 cm<sup>-1</sup> peak showed that the twisting motion appears after a 0.5 ps delay after photoexcitation, which supported the hypothesis that the molecule proceeded through an intermediate state. The technique that I developed in this study can be applied to study other systems, and the <a href="{{ '/projects/3_OscillationsApp/' | absolute_url }}">OscillationsApp</a> project page has more details about the interactive web application that simplifies the analysis for this type of data. Additionally, the poster below provides more details regarding the project.

<div class="center-block text-center">
  <a class="btn btn-sm" role="button" href="{{ '/assets/pdf/Physcon-HBDI.pdf' | absolute_url }}">HBDI Poster</a>
</div>