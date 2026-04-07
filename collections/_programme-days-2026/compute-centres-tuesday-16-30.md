---
# ============================================================
# TALKS
# Please complete all required fields before submitting a PR.
# ============================================================



# -------------------------
# SCHEDULING INFORMATION - COMPLETE INFORMATION

# Full TITLE of the session/tutorial
title: "HPC Centres"



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
speaker: "Cristin Merritt, Richard Knepper, Syed Ibtisam Tauhidi"
# Speakers photos (must match order of names above). 
speaker_photos:
  - "assets/images/generic.jpg"
  - "assets/images/generic.jpg"
  - "assets/images/syed_tauhidi.jpg"
# Speakers profile links (must match order of names above)
speaker_links:
  - ""
  - ""
  - "https://www.linkedin.com/in/ibtisamtauhidi/"




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

<h3>Every Supercomputer is a Record of Decisions: Navigating New Tensions in HPC • Cristin Merritt </h3>
High-Performance Computing systems are often discussed in terms of architecture, performance, and scale. Yet every HPC system is ultimately shaped by a series of decisions: what hardware to buy, how resources are allocated, which users are prioritised, and how policies evolve over time.<br>

This short, interactive talk explores HPC systems through the lens of decision-making. Using live polls and discussions, we will take the community's pulse at Durham HPC Days and examine the factors that most influence operational and infrastructure decisions across HPC centres.<br>

Participants will be invited to consider common decision scenarios reflecting the tensions HPC centres face today, including capacity planning, scheduler policies, user growth, and strategic direction.<br>

The session will also introduce Season 2 of Move the Needle: Decision Making in HPC, a community project exploring how HPC centres make decisions and how small improvements in decision processes can lead to better outcomes for researchers, operators, and institutions.

<h3>What's next? Genesis Mission, NAIRR, and the next phase of science in the US • Richard Knepper </h3>
The US Department of Energy has initiated the Genesis mission to 'double the science productivity of the US', the National AI Research Resource is moving beyond its Pilot Phase, and the National Institutes of Health and National Science Foundation have had massive restructuring in the interim. Meanwhile, regional initiatives like New York's Empire AI and California Compute are beginning to take shape. This talk describes what new developments are being built, what directions are encouraged under funding initiatives, and where the US computational research community may be pointed as it moves forward. This discussion will cover new computational investments (and changes to how those investments takes shape), new points of focus from the administration, and maybe even some discussion of those difficult supply chain issues.




<h3>A Frequency-Invariant Approach to Energy-Efficient Computing • Syed Ibtisam Tauhidi </h3>
Modern CPUs use Dynamic Voltage and Frequency Scaling (DVFS) to manage the explosive growth in energy consumption in computation, including in High-Performance Computing (HPC) and AI inference workloads. However, standard governors rely on coarse utilisation heuristics, operating on a 'race-to-idle' philosophy, assume that high CPU utilisation correlates with productive computation. This assumption collapses during memory-bound phases, such as LLM token generation or sparse matrix operations, where cores are stalled due to cache misses, despite utilisation remaining near 100%. Thus, such systems waste energy maintaining peak frequencies waiting for cache fill. Previous software solutions face adoption barriers, demanding intrusive source code modifications, offline training, or dense telemetry with heavy overhead. <br><br>

In this talk, I present URJA, a purely online, user-space DVFS framework that eliminates energy waste without disrupting workflows. URJA employs a minimalist design using a sparse set of hardware counters, specifically Last-Level Cache Misses Per Kilo Instruction (MPKI). We demonstrate MPKI is a robust, frequency-invariant proxy for memory pressure, enabling accurate phase classification without dynamic recalibration. To prevent control thrashing, URJA replaces continuous scaling with a reactive ternary control model (minimum, maximum, and stable intermediate frequencies) combined with adaptive window-based smoothing and hysteresis. Furthermore, the control parameters for our DVFS framework are rigorously derived using various data-driven methodologies. Comprehensive evaluations across Intel and ARM platforms using NAS Parallel Benchmarks, SPEC CPU2017, and LLM inference tasks (Ministral 3, GPT-OSS) demonstrate URJA's efficacy. URJA drives execution toward the Energy-Delay Product (EDP) Pareto frontier, achieving a ~10% EDP improvement. It yields up to 29% energy savings without significant runtime degradation, maintaining a negligible ~1% overhead."


   

requirements: ""


# -------------------------
# SCHEDULING INFORMATION - PLEASE DO NOT TOUCH THIS PART
# -------------------------



layout: talk
category: "talk"


day: "Tuesday"
track: "B"

start_time: "16:30"
end_time: "18:00"


day_1: "Tuesday"
start_time_1: "16:30"
end_time_1: "18:00"




room: "Mountjoy Centre"



---
