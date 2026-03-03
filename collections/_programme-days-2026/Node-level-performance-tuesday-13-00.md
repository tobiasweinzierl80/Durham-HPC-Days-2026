---
# ============================================================
# TUTORIAL
# Please complete all required fields before submitting a PR.
# ============================================================



# -------------------------
# SCHEDULING INFORMATION - COMPLETE INFORMATION

# Full TITLE of the session/tutorial
title: "Node-level performance optimisation"


# Comma-separated list of INSTRUCTORS
instructor: "Georg Hager, Thomas Gruber"

# INSTRUCTORS photos (must match order of names above). 
instructor_photos:
  - "https://github.com/hpc-days/Durham-HPC-Days-2026/blob/main/assets/images/generic.jpg?raw=true"
  - "https://github.com/hpc-days/Durham-HPC-Days-2026/blob/main/assets/images/generic.jpg?raw=true"
  
# Instructor profile links (must match order of names above)
instructor_links:
  - "https://hpc.fau.de/person/georg-hager/"
  - "https://hpc.fau.de/person/thomas-gruber/"

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
institution_logo: "https://hpc.fau.de/files/2023/11/cropped-NHRatFAU-Logo-mSchriftzug.png"
# Institution website link
institution_link: "https://www.fau.eu/"



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

# Full session description (please use <br> to add a new paragraph) 
description: "This course covers performance engineering approaches on the compute node level.
<br><br>
Even application developers who are fluent in OpenMP and MPI often lack a good grasp of how much performance could at best be achieved by their code. This is because parallelism takes us only half the way to good performance. Even worse, slow serial code tends to scale very well, hiding the fact that resources are wasted. This course conveys the required knowledge to develop a thorough understanding of the interactions between software and hardware. This process must start at the core, socket, and node level, where the code gets executed that does the actual computational work. We introduce the basic architectural features and bottlenecks of modern processors and compute nodes. Pipelining, SIMD, superscalarity, caches, memory interfaces, ccNUMA, etc., are covered. A cornerstone of node-level performance analysis is the Roofline model, which is introduced in due detail and applied to various examples from computational science. We also show how simple software tools can be used to acquire knowledge about the system, run code in a reproducible way, and validate hypotheses about resource consumption. Finally, once the architectural requirements of a code are understood and correlated with performance measurements, the potential benefit of code changes can often be predicted, replacing hope-for-the-best optimizations by a scientific process"
   

requirements: ""


# -------------------------
# SCHEDULING INFORMATION - PLEASE DO NOT TOUCH THIS PART
# -------------------------



layout: tutorial
category: "Tutorial"


day: "Tuesday"
track: "A"
start_time: "13:00"
end_time: "14:30"


day_1: "Tuesday"
start_time_1: "09:00"
end_time_1: "10:30"

day_2: "Tuesday"
start_time_2: "13:00"
end_time_2: "14:30"

day_3: "Tuesday"
start_time_3: "16:30"
end_time_3: "18:00"




room: "Mountjoy Centre"



---

