---
# ============================================================
# TALKS
# Please complete all required fields before submitting a PR.
# ============================================================



# -------------------------
# SCHEDULING INFORMATION - COMPLETE INFORMATION

# Full TITLE of the session/tutorial
title: "HPC Code development"



#FACILITATOR
# Comma-separated list of the facilitator of the session
facilitator: "TBD"
# facilitator photos (must match order of names above). 
facilitator_photos:
  - "assets/images/generic.jpg"
# facilitator profile links (must match order of names above)
facilitator_links:
  - ""


#SPEAKERS
# Comma-separated list of the speakers of the session
speaker: "Mikolaj Adam Kowalski, Dmitry Nikolaenko"
# Speakers photos (must match order of names above). 
speaker_photos:
  - "assets/images/generic.jpg"
  - "assets/images/generic.jpg"
# Speakers profile links (must match order of names above)
speaker_links:
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
description: "This session will feature these talks:

<h3>Statistical unit testing of sampling algorithms • Mikolaj Adam Kowalski </h3>
In general, one expects unit test suites for any code to be fully deterministic. However, one application where this assumption cannot be fully fulfilled is the development of particle transport Monte Carlo codes, which require implementing a vast number of sampling algorithms for non-standard distributions. While these can be tested for regression using reproducible random number sequences, this type of testing cannot confirm the correctness of the sampling algorithm itself. In addition, it is problematic for development, as even cosmetic changes that do not affect statistical correctness can alter the random number sequence and cause regression tests to fail.

Hence, in practice, sampling algorithms are often not covered by automated test suites and are only verified periodically in lengthy V&V (Verification and Validation) campaigns before new version releases. Naturally, this makes experimenting with alternative implementations or identifying correctness errors difficult.

This talk will cover an experimental Rust library, test-sampler, whose goal is to provide a unit testing framework for the verification of sampling algorithms. It is based on two-sample statistical tests between reference samples—drawn from a shape function describing the probability density function (PDF) of a distribution (which can be verified using standard unit testing frameworks)—and samples drawn from the test distributions. Currently, the framework implements the Kolmogorov-Smirnov, Kuiper, and Anderson-Darling tests. In this talk, I will discuss how the library works and attempt to quantify the effectiveness, in terms of the 'power' of these tests, when applied to algorithms containing programming errors.

<h3>Peano and load balancing • Dmitry Nikolaenko </h3>
Peano is an open-source framework for dynamically adaptive Cartesian meshes derived from spacetrees. It ties mesh traversal to mesh storage through space-filling curves (SFC), enabling scalable simulations on shared- and distributed-memory supercomputers. The framework underpins several scientific codes, including ExaHyPE 2 (hyperbolic PDE solvers) and Swift 2 (particle methods), and targets modern HPC platforms ranging from multicore workstations to GPU-accelerated supercomputer nodes.

At the heart of Peano lies a hierarchical spacetree that is constructed level by level during the simulation set-up. Each node of this tree represents a spatial cell; leaves carry the actual computational work. As the mesh grows, the distribution of leaves across MPI ranks and CPU threads becomes uneven, leading to idle processors and wasted wall-clock time. Achieving a balanced partition is therefore critical for strong scaling.

Peano's load balancing toolbox provides a suite of strategies — from simple spread-out schemes to recursive bipartition and cascade combinators — each triggering splitting calls at the right moment to redistribute subtrees across compute resources. A key challenge is that splitting decisions must be made online, without knowledge of the final mesh structure, while the cost of moving data grows with the current tree size.

In this talk we present an offline load balancing approach that transforms this online problem: the mesh is first constructed without any decomposition and checkpointed; an offline analysis tool then inspects the complete spacetree, derives an optimal multi-level splitting sequence, and encodes it as a hardcoded strategy for a warm restart. We describe the Python API that automates this workflow — including leaf distribution, bottom-up topology propagation, and a planned hierarchical optimisation stage that minimises splitting cost whilst preserving load balance — and share lessons learned from applying it to black-hole simulations with the CCZ4 solver in ExaHyPE 2."
   

requirements: ""


# -------------------------
# SCHEDULING INFORMATION - PLEASE DO NOT TOUCH THIS PART
# -------------------------



layout: talk
category: "talk"


day: "Thursday"
track: "B"

start_time: "09:00"
end_time: "10:30"


day_1: "Thursday"
start_time_1: "09:00"
end_time_1: "10:30"




room: "Mountjoy Centre"



---
