---
# ============================================================
# TALKS
# Please complete all required fields before submitting a PR.
# ============================================================



# -------------------------
# SCHEDULING INFORMATION - COMPLETE INFORMATION

# Full TITLE of the session/tutorial
title: "Computational Engineering"



#FACILITATOR
# Comma-separated list of the facilitator of the session
facilitator: "Gokberk Kabacaoglu"
# facilitator photos (must match order of names above). 
facilitator_photos:
  - "assets/images/generic.jpg"
# facilitator profile links (must match order of names above)
facilitator_links:
  - ""


#SPEAKERS
# Comma-separated list of the speakers of the session
speaker: "Ashutosh Shankarrao Londhe, Vahid Jafari, Henrique Bergallo Rocha, Robert Bird"
# Speakers photos (must match order of names above). 
speaker_photos:
  - "assets/images/generic.jpg"
  - "assets/images/profile/vahid.jpg"
  - "assets/images/generic.jpg"
  - "assets/images/generic.jpg"
# Speakers profile links (must match order of names above)
speaker_links:
  - ""
  - ""
  - ""




# -------------------------







# ------------------------------------------------
# AFFILIATION / DELIVERY INFORMATION
# Please complete ONLY ONE of the sections below when applicable:


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
description: "This session will feature three talks:

<h3>Advancing DNS Turbulent Reacting Flow Simulations with Performance Portability Using OPS • Ashutosh Shankarrao Londhe</h3>
This session introduces computational engineering concepts.<br><br>
SENGA+ is a high-order finite difference compressible direct numerical simulation (DNS) code for simulating turbulent reacting flows. It incorporates detailed chemical reactions and transport with high order numerical schemes to achieve high-fidelity simulations and excellent parallel scaling. This talk presents our experience in deploying SENGA+ on next-generation high-performance computing systems, using the OPS DSL. We discuss the key challenges encountered during the porting process, underpinned by specialized optimizations to gain near-optimal performance on multi-core/many-core systems. OPS enables automatic generation of multiple parallelizations, highly customized for the target architectures, reducing developer effort and increasing code longevity. Performance evaluation shows up to 22× speedup on a GPU node with 4 AMD MI250X compared to the original CPU-only code. We also present validation simulations using the re-engineered application with near-optimal scaling on up to 2k GPUs. The new code enables simulating production-level combustion problems at high-fidelity within tractable time-frames that were previously prohibitively expensive.

<h3>Scalable Coupled CFD–DSMC Simulations for Hypersonic Flows: Accuracy–Performance Trade-offs on Modern HPC Systems • Vahid Jafari </h3>
Hypersonic flows in transitional and rarefied regimes present significant modelling challenges, as continuum assumptions progressively break down and neither classical CFD nor particle-based approaches alone are sufficient. This work presents a coupled CFD–DSMC framework for hypersonic flow simulations, integrating an in-house finite-volume CFD solver with the SPARTA DSMC code through the Macro-Micro-Coupling (MaMiCo) tool. The approach employs spatial domain decomposition to restrict DSMC calculations to non-equilibrium regions, thereby avoiding the prohibitive cost of full-domain particle simulations.

Rarefied gas behaviour in transitional regimes is investigated, with emphasis on consistency and conservation properties across the CFD–DSMC coupling interface. Particular attention is given to the relationship between physical accuracy and computational cost on distributed-memory HPC systems.

In DSMC simulations, increasing the number of simulation particles leads to a steep rise in computational cost, limiting achievable particle densities in large-scale problems. To reduce statistical fluctuation errors without excessively increasing particle numbers within a single simulation, multiple independent DSMC instances are executed concurrently. Ensemble averaging of these independent realisations improves statistical convergence while maintaining feasible per-instance computational requirements.

Error estimation capabilities provided by the Macro-Micro-Coupling (MaMiCo) tool are used to quantify statistical and coupling uncertainties, enabling a systematic assessment of the trade-off between accuracy and computational effort. Performance characteristics—including runtime, parallel scalability, memory footprint, and energy consumption—are analysed for different coupling configurations and DSMC ensemble sizes.

The results provide practical guidelines for selecting particle numbers, DSMC subdomain sizes, and ensemble strategies, enabling efficient and scalable high-fidelity simulations of hypersonic transitional flows on modern HPC architectures.

<h3>Finite Element Method Scaling and Performance on MI300X GPUs Through MFEM-Enabled MOOSE • Henrique Bergallo Rocha</h3>
With the new generation of GPU-accelerated HPC systems opening new avenues in large-scale physical modelling, nuclear fusion applications through the Finite Element Method (FEM) require code that is performant at scale, parallelisable, and that can faithfully reproduce highly coupled, complex multiphysics on meshes with up to O(10^10) degrees of freedom. MFEM-Enabled MOOSE, i.e. a build of the MOOSE framework that utilises the MFEM FEM library as opposed to libMesh, has been shown to fulfil these requirements on CPUs and on GPUs with a CUDA backend. However, so far the scalability and general performance of MFEM-Enabled MOOSE on recent AMD hardware has not been explored to great extent, which may turn to be a blind spot when it comes to the deployment of large HPC systems in the UK with AMD GPUs. In this talk, we present our results from benchmarking, profiling, and measuring the scalability of MFEM-Enabled MOOSE on the MI300X nodes in the CSD3 system. We perform weak and strong scaling analyses across a variety of sample FEM problems utilising different solvers and preconditioners. The sample problems studied represent different kinds of physics and span the entire De Rham complex, and they are tested to up to O(10^2) GPU cards on a single problem. We then compare these results to those tested on equivalent NVIDIA hardware and discuss their relative strengths and weaknesses.


<h3>Title • Robert Bird</h3>
Description"
   

requirements: ""


# -------------------------
# SCHEDULING INFORMATION - PLEASE DO NOT TOUCH THIS PART
# -------------------------



layout: talk
category: "talk"

day: "Wednesday"
track: "D"
start_time: "09:00"
end_time: "10:30"

day_1: "Wednesday"
start_time_1: "09:00"
end_time_1: "10:30"



room: "Mountjoy Centre"



---
