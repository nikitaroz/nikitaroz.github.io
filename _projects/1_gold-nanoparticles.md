---
layout: project_page
title: Gold Nanoparticles and Cytochrome *c*
description: My research at Johns Hopkins University centered around understanding how the cytochrome *c* protein interacts with gold nanoparticles.
img: /assets/img/MPA-nanoparticle.png
importance: 1
---

# Introduction
Gold nanoparticles (AuNPs) are increasingly used as transporters of novel medicines and in other applications. During my time at the Hernandez group at Johns Hopkins University, I researched how AuNPs interact with cytochrome *c* using molecular dynamics (MD) simulations. MD simulations use Newtonian mechanics to simulate molecular systems, and they are especially useful for larger systems such as proteins where quantum mechanical calculations would be computationally intractable. These simulations helped uncover how AuNPs with different surface coatings interact with cytochrome *c*, an important biological protein, with the purpose of designing safer nanoparticles. This research was conducted as part of the Center of Sustainable Nanotechnology, which focuses on understanding the health and safety implications of nanoparticles.

# MPA nanoparticles
3-mercaptopropionic acid (MPA) is a small, highly-charged molecule, and it was the first nanoparticle coating that I studied. I wanted to find a way determine which sites on cytochrome *c* will bind to the nanoparticle. To set up this study, I modeled the protein as having six faces (like the sides of a dice), and I created six simulations with each of the different faces was oriented towards the nanoparticle, arranged like so. 
<img class="img-responsive mx-auto d-block" style="width: 90%;" src="{{ '/assets/img/MPA-nanoparticle.png' | absolute_url }}" alt="MPA configurations">

The protein was placed at a short distance away from the AuNP to allow for it to optimize its orientation for the best binding, but is not too far away that it does not bind to the AuNP. Once the protein binds to the surface coating, the simulation continues, allowing the protein to position itself into a more favorable configuration if one exists. Each of these simulations had over 100 thousand atoms, and was run for a 50 nanosecond duration (equivalent to 25 million individual timesteps). 

Once these simulations completed, I analyzed how the nanoparticle interacted with the protein. One simple measure of protein to nanoparticle affinity is the distance between the (center of) the nanoparticle and different parts of the protein surface. This works because the nanoparticle is spherical. I also tracked the number of hydrogen bonds during the simulation, which provide another measure of affinity. Putting these two pieces of evidence together, I determined that the two protein sites, known as A and L, interacted most strongly with the nanoparticle coating. 
<img class="img-responsive mx-auto d-block" style="width: 90%;" src="{{ '/assets/img/MPA-affinity.svg' | absolute_url }}" alt="MPA affinity graph">
Additionally, I looked at which specific amino acid residues interacted with the MPA nanoparticle. determined lysine amino acids interacted strongly with the coating, and, as one would expect, the -- and -- sites contained lysines. 
<img class="img-responsive mx-auto d-block" style="width: 90%;" src="{{ '/assets/img/MPA-affinity-detail.svg' | absolute_url }}" alt="MPA affinity residue graph">
From this figure, it is clear that lysine residues (labeled K in the figure) interact strongly with the MPA, an important finding. 

# EG6 nanoparticles
Hexa(ethylene glycol) (EG6) is a much larger, non-polar, molecule than MPA, which presented a unique set of challenges when compared to MPA. The EG6 coating is more uneven and has variable thickness, which made it more challenging to quantify its interaction with the protein. For example, we could no longer use distance to the nanoparticle as an accurate measure of interaction because the variable thickness of the coating. 

<img class="img-responsive mx-auto d-block" style="width: 90%;" src="{{ '/assets/img/EG6-nanoparticle-preparation.png' | absolute_url }}" alt="EG6 nanoparticle preparation">

To overcome this challenge, I redefined how the interaction distance to be the distance between a site on the protein and the nearest atom that was part of the surface coating. Additionally, how could we know how much of the protein surface was exposed to the nanoparticle (ie. coverage)? To determine this, I modeled the protein as a rigid body with three principal axes. There is a line between the protein's center of mass and the nanoparticle's center, and this line makes a distinct angle with respect to the principal axes. Tracking this angle throughout all simulations allowed us to quantify the protein's coverage. 

We found that the interaction cytochrome *c* was much more limited for the EG6 coating when compared to the MPA one. This suggested that non-polar molecules are less interactive toward cytochrome *c*. 

# Conclusion
My research on AuNP interactions with cytochrome *c* showed how surface coatings affect protein interaction. We found that the small, highly-charged MPA molecule interacts strongly with the lysines on the surface of cytochrome *c*, which makes the A and L sites, which contain lysines, binding candidates. In contrast, the non-polar EG6 coating does not significantly interact with cytochrome *c*. This has major implications into how nanoparticle coatings can be designed to prevent unintended proteins from binding, potentially leading to safer surface coating formulations.

If you are interested in learning more about this project, check out the posters I presented.
<div class="center-block text-center">
  <a class="btn btn-sm" role="button" href="{{ '/assets/pdf/JHU-MPA-coated-NPs.pdf' | absolute_url }}">MPA Poster</a>
  <a class="btn btn-sm" role="button" href="{{ '/assets/pdf/JHU-EG6-coated-NPs.pdf' | absolute_url }}">EG6 Poster</a>
</div>