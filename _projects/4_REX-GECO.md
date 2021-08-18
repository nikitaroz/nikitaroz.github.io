---
layout: project_page
title: REX-GECO Structure
description: Simulations and homology modeling to determine REX-GECO protein structure.
img: /assets/img/REX-GECO.png
importance: 4
---

# Introduction
REX-GECO is a calcium biosensor fluorescent protein developed in 2014. It is ...  The protein contains a calcium binding region, and when calcium binds to the protein, its fluorescence color changes. REX-GECO has a drastic change in fluorescence color after it binds calcium, larger than for most other proteins of its type. This protein is useful to study because the large color change a beneficial property for bioimaging. In my project I estimated the structure of this protein using homology modeling and molecular dynamics (MD) simulations.

# Homology Modeling
The REX-GECO protein consists of three comonents: a fluorescent protein fragment, a Calmodulin (CaM) calcium binding region, and a myosin light chain kinase (M13) region that interacts with CaM during calcium binding. 

<img class="img-responsive mx-auto d-block" style="width: 90%;" src="{{ '/assets/img/REX-GECO-proteins.png' | absolute_url }}" alt="REX-GECO calcium binding diagram" data-zoomable>


When calcium ions bind to CaM, its structure changes drastically, and this change also impacts the adjacent fluorescent protein region, causing its photochemistry to change. To determine what these structural differences are, I created 5 structural predictions for the protein with and without calcium. REX-GECO does not have a structure that has been determined from experiments. However, the structure for its parent protein, R-GECO, is available (pdb: 4i2y). I used the MODELLER homology modeling software to generate structural predictions. Homology modeling is a method for generating predictions for unknown protein structures using structures from already known structures. This software takes one or more protein structures along with their amino acid sequences, and uses this information to predict the structure of a target amino acid sequence.

# Molecular Dynamics Simulations
Next, I performed molecular dynamics (MD) simualtions on each of these generated structures. These simulations provide many structural snapshots of the protein, which I then used to predict aggregate structural properties. Each of these simulations was carried out for xx million steps, and a snapshot of the system is saved every ... steps. Once they completed, I collected the saved snapshots and analyzed them in Python using the MDAnalysis package.

# Results
The dihedral angles on the chromophore are important structural features that influence the photochemistry of the protein. The chromophore is molecular fragment that is responsible for the protein's fluorescence, and it is shown below.

<img class="img-responsive mx-auto d-block" style="width: 50%;" src="{{ '/assets/img/REX-GECO-dihedral-diagram.svg' | absolute_url }}" alt="REX-GECO dihedral diagram" data-zoomable>


I measured the distribution of the $$\tau$$ and $$\phi$$ dihedral angles shown in the figure. After aggregating the measurements from all 10 simulations, I plotted the density estimate of the angle distribution.

<img class="img-responsive mx-auto d-block" style="width: 70%;" src="{{ '/assets/img/REX-GECO-dihedrals.svg' | absolute_url }}" alt="REX-GECO dihedral angle distribution">

On average, $$\tau$$ is xx when calcium is bound to the protein and xx when it is not, similarly, $$\phi$$ is xx and xx for the same situation. These distributions show that both the $$\tau$$ and $$\phi$$ angles tend to be larger in magnitude when calcium is not bound to the protein. This suggests that the chromophore is more twisted when there is no calcium present. Combining this observation with experimental results, a theory for why the two protein forms differ in their photochemistry emerged: the more twisted state .......




<div class="center-block text-center">
  <a class="btn btn-sm" role="button" href="{{ '/assets/pdf/Senior-Thesis.pdf' | absolute_url }}">Senior Thesis</a>
</div>