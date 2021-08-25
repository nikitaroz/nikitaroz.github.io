---
layout: project_page
title: Gold Nanoparticles and Cytochrome *c*
simple_title: Gold Nanoparticles and Cytochrome c
description: My research at Johns Hopkins University centered around understanding cytochrome *c* interacts with gold nanoparticles.
img: /assets/img/MPA-nanoparticle.png
importance: 1
---

# Introduction
Gold nanoparticles (AuNPs) are increasingly finding applications in medicine as transporters of drug molecules. During my time at the Hernandez group at Johns Hopkins University, I researched how AuNPs interact with cytochrome *c* using molecular dynamics (MD) simulations. MD simulations use Newtonian mechanics to simulate molecular systems, and they are especially useful for larger systems such as proteins where quantum mechanical calculations would be computationally intractable. These simulations helped uncover how AuNPs with different surface coatings interact with cytochrome *c*, an important biological protein. This research was conducted as part of the Center for Sustainable Nanotechnology with the goal of designing safer nanoparticles.

# MPA nanoparticles
The first nanoparticle coating that I studied was 3-mercaptopropionic acid (MPA): a small, highly-charged molecule. I wanted to determine which sites on cytochrome *c* will bind to the nanoparticle. To achieve this goal, I modeled the protein as having six faces (like the sides of a dice), and I created six simulations where each of the different faces was oriented towards the nanoparticle, arranged like so. 
<img class="img-responsive mx-auto d-block" style="width: 80%;" src="{{ '/assets/img/MPA-nanoparticle.png' | absolute_url }}" alt="MPA configurations">
The protein was placed at a short distance away from the AuNP to allow for it to optimize its orientation for the best binding, but is not too far away that it does not bind to the AuNP. Once the protein binds to the surface coating, the simulation continues, allowing the protein to position itself into a more favorable configuration. Each of these simulations had over 100 thousand atoms, and proceeded for a 50 nanosecond duration, the equivalent of 25 million individual timesteps.

Once these simulations completed, I analyzed how the nanoparticle interacted with the protein. One simple measure of protein-to-nanoparticle affinity is the distance between the (center of) the nanoparticle and the protein surface. This approach works because the nanoparticle is spherical, so this distance measures how close the protein surface is to the nanoparticle. Additionally, I tracked the number of hydrogen bonds during the simulation, which is another measure of affinity. The figure below illustrates which residues on the protein had the greatest affinity based on these measurements.

<img class="img-responsive mx-auto d-block" style="width: 90%;" src="{{ '/assets/img/MPA-affinity.svg' | absolute_url }}" alt="MPA affinity graph">

Two protein sites, known as A and L, interacted strongly with the nanoparticle's MPA coating. Another way to visualize the same data is to show the individual amino acids that interact most strongly with the AuNP. These residues are shown below.

<img class="img-responsive mx-auto d-block" style="width: 90%;" src="{{ '/assets/img/MPA-affinity-detail.svg' | absolute_url }}" alt="MPA affinity residue graph">

The figure shows that the lysine residues (labeled K) interact strongly with the MPA, another important finding. And, as one would expect, the A and L sites contained lysines.

# EG6 nanoparticles
Hexa(ethylene glycol) (EG6) is a non-polar and much larger molecule than MPA, which presented a unique set of challenges when compared to MPA. Namely, the size of EG6 makes it more challenging to construct the nanoparticle. The figure below summarizes how I prepared the nanoparticle: the EG6 molecules attached themselves to the gold core during a 4 nanosecond simulation.

<img class="img-responsive mx-auto d-block" style="width: 90%;" src="{{ '/assets/img/EG6-nanoparticle-preparation.png' | absolute_url }}" alt="EG6 nanoparticle preparation">

After completing similar simulations as with MPA, I found that the interaction between cytochrome *c* and the EG6-coated AuNP was limited. This suggests that non-polar molecules have less affinity towards cytochrome *c*. Additionally, I developed a method to determine how well the simulations covered the surface of the protein (more about that in the EG6 poster linked below).

# Conclusion
My research on AuNPs showed how surface coatings affect their interaction with cytochrome *c*. My research found that the small, highly-charged MPA molecule interacts strongly with the lysines on the surface of cytochrome *c*, making the A and L sites likely binding candidates. In contrast, the non-polar EG6 coating did not significantly interact with cytochrome *c*. This has major implications into how nanoparticle coatings can be designed to prevent unintended proteins from binding, potentially leading to safer surface coating formulations.

These posters go into more depth about the project.
<div class="center-block text-center">
  <a class="btn btn-sm" role="button" href="{{ '/assets/pdf/JHU-MPA-coated-NPs.pdf' | absolute_url }}">MPA Poster</a>
  <a class="btn btn-sm" role="button" href="{{ '/assets/pdf/JHU-EG6-coated-NPs.pdf' | absolute_url }}">EG6 Poster</a>
</div>