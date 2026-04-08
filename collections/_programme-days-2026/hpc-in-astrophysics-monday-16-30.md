---
# ============================================================
# TALKS
# Please complete all required fields before submitting a PR.
# ============================================================



# -------------------------
# SCHEDULING INFORMATION - COMPLETE INFORMATION

# Full TITLE of the session/tutorial
title: "HPC in Astrophysics and Astronomy"



#FACILITATOR
# Comma-separated list of the leads of the session
facilitator: "Mladen Ivkovic"
# Leads photos (must match order of names above).
facilitator_photos:
  - "assets/images/profile/mladenivkovic.jpg"
# Leads profile links (must match order of names above)
facilitator_links:
  - "https://www.durham.ac.uk/staff/mladen-ivkovic/"


#SPEAKERS
# Comma-separated list of the speakers of the session
speaker: "Sarah Johnston, Abouzied Nasar, Will Roper, Zhen Xiang, Romeel Dave, Kyle Oman, Britton Smith"
# Speakers photos (must match order of names above).
speaker_photos:
  - "assets/images/profile/sarahjohnston.png"
  - "assets/images/profile/abouziednasar.webp"
  - "assets/images/profile/willjroper.jpg"
  - "assets/images/generic.jpg"
  - "assets/images/profile/rdave.jpg"
  - "assets/images/profile/kyleoman.jpg"
  - "assets/images/profile/brittonsmith.jpg"
# Speakers profile links (must match order of names above)
speaker_links:
  - "https://sarahjohnston-astronomy.co.uk/"
  - "https://research.manchester.ac.uk/en/persons/abouzied.nasar"
  - "https://willjroper.github.io/about.html"
  - "https://www.ph.ed.ac.uk/people/zhen-xiang"
  - "https://www.ph.ed.ac.uk/people/romeel-dave"
  - "https://www.durham.ac.uk/staff/kyle-a-oman/"
  - "https://www.ph.ed.ac.uk/people/britton-smith"




# -------------------------







# ------------------------------------------------
# AFFILIATION / DELIVERY INFORMATION
# Please complete ONLY ONE of the sections below when applicable.:


# Use "institution" when listing the primary institutional
# affiliation of the session leads (e.g. university, lab, company).
# This represents where the speakers are based.

# Use "organiser" when an organisation is formally organising
# or hosting the session (e.g. a SIG, network, or research group
# responsible for delivering the workshop).

# Use "supported" when the session is funded, sponsored,
# or otherwise supported by a project or external organisation.


# INSTITUTION
# Comma-separated list of institutions
institution: ""
# Institution logo
institution_logo: ""
# Institution website link
institution_link: ""



# ORGANISER
# Comma-separated list of organisers
organiser: ""
# Organisers logo
organiser_logo: ""
# Organisers website link
organiser_link: ""


# SUPPORTED
# Comma-separated list of supporters
supported: ""
# Institution logo
supported_logo: ""
# Institution website link
supported_link: ""



# ------------------------------------------------


# -------------------------
# DESCRIPTION

# Full session description (please use <br> to add a new paragraph). Add requirements if relevant.
description: "HPC is an indispensable discipline in astrophysics and cosmology with many users running simulations, solving intricate networks of nonlinear equations, post-processing and analysing data, and synthesising images, spectra, and mock observations on a daily basis. Despite its crucial importance to the field, the presentation and discussion of our HPC work often falls short during astronomy and astrophysics conferences, which tend to focus on physics outputs and outcomes.

This session serves as a platform to exchange and highlight all the underlying HPC work, both current an in progress, as well as challenges in the astrophysics and astronomy communities.

<h2> Session Part 1 </h2>

<h3>
Making Gravity SWIFTer: GPU offloads for gravity in the SWIFT cosmology code • Sarah Johnston
</h3>
To fully utilise modern heterogeneous HPC systems and improve power efficiency, large astronomy codes must become GPU compatible. SWIFT is a versatile open-source cosmology code which is used to model a variety of astrophysical scenarios. It utilises task-based parallelism, dividing the workload into independent tasks managed by a scheduler for efficient CPU utilisation, and is highly optimised for use on memory-intensive, CPU-only clusters. A significant portion of SWIFT’s runtime is dedicated to gravity calculations. However, the repetitive and non-interdependent nature of these interactions makes them ideal candidates for GPU acceleration.
In this work, we build on the existing SWIFT code by replacing CPU-based gravity with new GPU kernels, while minimising changes to the rest of the code. The GPU-accelerated kernels achieve high accuracy, with <1% deviation from the CPU results. However, we are limited by a memory transfer bottleneck in moving data between the CPU and GPU. To mitigate this, we have employed a novel ‘task-bundling’ system which allows us to group tasks in the scheduler to give higher occupancy on the GPU. This provides more work, reducing the overhead from the CPU-GPU memory transfers.
To further exploit the GPU, we explore a redistribution of the gravity calculations meaning more interactions can be carried out using direct particle-particle summations, rather than multipole-based approximations, which gives us more accurate results and provides more work for the GPU. We also investigate kernel optimisations like the use of multiple streams and tiled memory access.


<h3>Exascale SWIFT hydrodynamics, are we there yet? • Abouzied Nasar</h3>
With the recent heavy lean towards heterogeneous solutions for supercomputing, the astrophysics solver SWIFT is being adapted to leverage GPUs and accelerate its computationally intense workloads such that it retains its world leading position as one of the most scalable and efficient publicy available solvers in the UK’s exascale era of supercomputing. SWIFT requires a plethora of solvers for different physics in order to create digital twins of the Universe and capture other smaller scale cosmological phenomena. The two most computationally demanding solvers are SWIFT’s hydrodynamics and gravity solvers. We therefore focus on these solvers initially with a view on extending the hard won benefits of GPU acceleration to other, less computationally demanding physics down the line. This talk focuses on the current state of GPU acceleration for the hydrodynamics solver within SWIFT’s task-parallel framework. We demonstrate significant speed ups in comparison to CPU-only baselines rivalling other world-leading GPU accelerated astrophysics solvers; GPU-accelerated SWIFT achieves 22 million particle time step updates per GPU per wall clock second in comparison to 8 million for the CPU code executed on a full 72 core CPU. We also present near-perfect computational scaling for the GPU accelerated solver and greater than 30% energy consumption savings in comparison to the CPU only baselines.

<h3>Swift-Zoom: Efficient and scalable zoom simulations • Will Roper </h3>

Zoom simulations are becoming an ever more important tool for investigating the Universe. Whether pushing volumes and resolution to the extreme to probe the rarest regions of the Universe, or sampling highly dimensional parameter spaces with numerous individual simulations, cosmological simulations are becoming increasingly costly, with many studies forced to compromise due to this expense. Zoom simulations alleviate this problem by focusing computational effort on the regions of interest for a particular problem, while degrading the resolution elsewhere, a simple proposition that makes the intractable tractable. However, these simulations are inherently unbalanced, and few codes (if any) have fully optimised their computations for this configuration. In this talk, I will present how we have optimised SWIFT for exactly this use case.

<h3> Simulating the Epoch of Reionization: Physical Complexity and Computational Challenges • Zhen Xiang </h3>
The Epoch of Reionization is the period when the first galaxies ionized the intergalactic medium. Simulating this process is challenging because it involves the interaction between radiation and gas across a wide range of scales.
In this talk, I will give a simple overview of these challenges and show how they appear in practice in cosmological simulations. Using examples from my work with Kiara-RT, a new radiation-hydrodynamics simulation suite, I will focus on the thermal evolution of gas and discuss how numerical choices affect the results. I will conclude with some open questions and future directions.

<h2> Session Part 2 </h2>

<h3> HPC Challenges in Next-Generation Galaxy Formation Simulations • Romeel Dave</h3>

I will give a brief overview of the current landscape in galaxy formation simulations, with a focus on our upcoming Kiara simulation suite.  The increasingly physics-rich and multi-scale modelling of a wide range of physical processes presents new challenges for HPC efficiency and scalability.  I will highlight some of the performance bottlenecks associated with Kiara, and identify possible ways forward including machine learning-based approaches and the use of GPUs.

<h3> The Grackle Chemistry and Cooling Library: What Happens Next • Britton Smith </h3>

Chemistry and radiative cooling are together a critical component of
galaxy simulations. Even employed with limited sophistication it is a
significant and often dominant portion of a simulation's computational
cost. As well, it represents a nearly infinitely hungry endeavor in
terms of both human and computational resources. The Grackle project
has provided an open-source library for chemistry and cooling with a
stable API that has been used in more than a dozen simulation codes
and hundreds of publications for over a decade. In this talk, I will
give a brief overview of the project and the functionality it provides
and present ongoing development efforts toward new features and
improved performance that will enable Grackle to support the next
generation of astrophysical simulations.

<h3> High-level tools for galaxy simulations analysis • Kyle Oman</h3>

Galaxy formation simulations produce large outputs with information-rich metadata catalogues. Some analysis tasks can be completed with the metadata alone, others require small, sparsely distributed subsamples of the full outputs, while others still require full datasets that may not fit in memory. Such diverse access patterns pose challenges for data storage and software tools for data access. I will give an overview of how we have addressed some of these in the swiftsimio and swiftgalaxy analysis packages, and highlight others that remain.
"




requirements: ""


# -------------------------
# SCHEDULING INFORMATION - PLEASE DO NOT TOUCH THIS PART
# -------------------------



layout: talk
category: "talk"

day: "Monday"
track: "B"

start_time: "16:30"
end_time: "18:00"


day_1: "Monday"
start_time_1: "13:00"
end_time_1: "14:30"

day_2: "Monday"
start_time_2: "16:30"
end_time_2: "18:00"


room: "Mountjoy Centre"



---

