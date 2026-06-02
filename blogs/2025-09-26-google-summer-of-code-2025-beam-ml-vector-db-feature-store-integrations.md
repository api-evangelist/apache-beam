---
title: Google Summer of Code 2025 - Beam ML Vector DB/Feature Store integrations
url: https://beam.apache.org/blog/gsoc-25-ml-connectors/
date: '2025-09-26'
author: ''
feed_url: https://beam.apache.org/feed.xml
---
What Will I Cover In This Blog Post? I have three objectives in mind when writing this blog post: Documenting the work I’ve been doing during this GSoC period in collaboration
with the Apache Beam community A thoughtful and cumulative thank you to my mentor and the Beam Community Writing to an older version of myself before making my first ever contribution
to Beam. This can be helpful for future contributors What Was This GSoC Project About? The goal of this project is to enhance Beam’s Python SDK by developing
connectors for vector databases like Milvus and feature stores like Tecton. These
integrations will improve support for ML use cases such as Retrieval-Augmented
Generation (RAG) and feature engineering. By bridging Beam with these systems,
this project will attract more users, particularly in the ML community. Why Was This Project Important? While Beam’s Python SDK supports some vector databases, feature stores and
embedding generators, the current integrations are limited to a few systems as
mentioned in the tables down below. Expanding this ecosystem will provide more
flexibility and richness for ML workflows particularly in feature engineering
and RAG applications, potentially attracting more users, particularly in the ML
community. Vector Database Feature Store Embedding Generator BigQuery Vertex AI Vertex AI AlloyDB Feast Hugging Face Why Did I Choose Beam As Part of GSoC Among 180+ Orgs? I chose to apply to Beam from among 180+ GSoC organizations because it aligns
well with my passion for data processing systems that serve information
retrieval systems and my core career values: Freedom: Working on Beam supports open-source development, liberating
developers from vendor lock-in through its unified programming model while
enabling services like Project Shield to protect free
speech globally Innovation: Working on Beam allows engagement with cutting-edge data
processing techniques and distributed computing paradigms Accessibility: Working on Beam helps build open-source technology that
makes powerful data processing capabilities available to all organizations
regardless of size or resources. This accessibility enables projects like
Project Shield to provide free protection to media, elections, and human rights
websites worldwide What Did I Work On During the GSoC Program? During my GSoC program, I focused on developing connectors for vector databases,
feature stores, and embedding generators to enhance Beam’s ML capabilities.
Here are the artifacts I worked on and what remains to be done: Type System Artifact Enrichment Handler Milvus PR #35216 PR #35577 PR #35467 Sink I/O Milvus PR #35708 PR #35944 Enrichment Handler Tecton PR #36062 Sink I/O Tecton PR #36078 Embedding Gen OpenAI PR #36081 Embedding Gen Anthropic To Be Added Here are side-artifacts that are not directly linked to my project: Type System Artifact AI Code Review Gemini Code Assist PR #35532 Enrichment Handler CloudSQL PR #34398 PR #35473 Pytest Markers GitHub CI PR #35655 PR #35740 PR #35816 For more granular contributions, checking out my ongoing Beam contributions . How Did I Approach This Project? My approach centered on community-driven design and iterative implementation,
Originally inspired by my mentor’s work. Here’s how it looked: Design Document : Created a comprehensive design document outlining the
proposed ML connector architecture Community Feedback : Shared the design with the Beam developer community
mailing list for review Iterative Implementation : Incorporated community feedback and applied
learnings in subsequent pull requests Continuous Improvement : Refined the approach based on real-world usage
patterns and maintainer guidance Here are some samples of those design docs: Component Type Design Document Milvus Vector Enrichment Handler [Proposal][GSoC 2025] Milvus Vector Enrichment Handler for Beam Milvus Vector Sink I/O Connector [Proposal][GSoC 2025] Milvus Vector Sink I/O Connector for Beam Tecton Feature Store Enrichment Handler [Proposal][GSoC 2025] Tecton Feature Store Enrichment Handler for Beam Tecton Feature Store Sink I/O Connector [Proposal][GSoC 2025] Tecton Feature Store Sink I/O Connector for Beam Where Did Challenges Arise During The Project? There were 2 places where challenges arose: Running Docker TestContainers in Beam Self-Hosted CI Environment: The main
challenge was that Beam runs in CI on Ubuntu 20.04, which caused compatibility
and connectivity issues with Milvus TestContainers due to the Docker-in-Docker
environment. After several experiments with trial and error, I eventually tested
with Ubuntu latest (which at the time of writing this blog post is Ubuntu 25.04),
and no issues arose. This version compatibility problem led to the container
startup failures and network connectivity issues Triggering and Modifying the PostCommit Python Workflows: This challenge
magnified the above issue since for every experiment update to the given
workflow, I had to do a round trip to my mentor to include those changes in the
relevant workflow files and evaluate the results. I also wasn’t aware that
someone can trigger post-commit Python workflows by updating the trigger files
in .github/trigger_files until near the middle of GSoC. I discovered there is
actually a workflows README document in .github/workflows/README.md that was
not referenced in the CONTRIBUTING.md file at the time of writing this post How Did This Project Start To Attract Users in the ML Community? It is observed that after we had a Milvus Enrichment Handler PR before even
merging, we started to see community-driven contributions like this one that adds Qdrant . Qdrant
is a competitor to Milvus in the vector space. This demonstrates how
the project’s momentum and visibility in the ML community space attracted
contributors who wanted to expand the Beam ML ecosystem with additional vector
database integrations. How Did This GSoC Experience Working With Beam Community Shape Me? If I have to boil it down across three dimensions, they would be: Mindset: Before I was probably working in solitude making PRs about new
integrations with mental chatter in the form of fingers crossed, hoping that
there will be no divergence on the design. Now I can engage people I am working
with through design docs, making sure my work aligns with their vision, which
potentially leads to faster PR merges Skillset: It was one year before contributing to Beam where I wrote
professionally in Python, so it was a great opprtunity to brush up on my Python
skills and seeing how some design patterns are used in practice, like the query
builder pattern seen in CloudSQL Vector Ingestion in the RAG package. I also
learned about vector databases and feature stores, and also some AI
integrations. I also think I got a bit better than before in root cause analysis
and filtering signals from noise in long log files like PostCommit Python
workflows Toolset: Learning about Beam Python SDK, Milvus, Tecton, Google CloudSQL,
OpenAI and Anthropic text embedding generators, and lnav for effective log file
navigation, including their capabilities and limitations Tips for Future Contributors If I have to boil them down to three, they would be: Observing: Observing how experienced developers in the Beam dev team
work—how their PRs look, how they write design docs, what kind of feedback they
get on their design docs and PRs, and how you can apply it (if feasible) to
avoid getting the same feedback again. What kind of follow-up PRs do they create
after their initial ones? How do they document and illustrate their work? What
kind of comments do they post when reviewing other people’s related work? Over
time, you build your own mental model and knowledge base on how the ideal
contribution looks in this area. There is a lot to learn and explore in an
exciting, not intimidating way Orienting: Understanding your place in the ecosystem and aligning your
work with the project’s context. This means grasping how your contribution fits
into Beam’s architecture and roadmap, identifying your role in addressing
current gaps, and mapping stakeholders who will review, use, and maintain your
work. Most importantly, align with both your mentor’s vision and the community’s
vision to ensure your work serves the broader goals Acting: Acting on feedback from code reviews, design document discussions,
and community input. This means thoughtfully addressing suggested changes in a
way that moves the discussion forward, addressing concerns raised by
maintainers, and iterating on your work based on community guidance. Being
responsive to feedback, asking clarifying questions when needed, and
demonstrating that you’re incorporating the community’s input into your
contributions given that it is aligned with the project direction Who Do I Want To Thank for Making This Journey Possible? If I have to boil them down to three, they would be: My Mentor, Danny McCormick: I wouldn’t hesitate to say that Danny is the
best mentor I have worked with so far, given that I have worked with several
mentors. What makes me say that: Generosity: Danny is very generous with his time, feedback, and
genuinely committed to reviewing my work on a regular basis. We have weekly
30-minute sync calls over almost 21 weeks (5 months) since the official
community bonding period, where he shares with me his contextual expertise and
addresses any questions I may have with openness to extend time if needed and
flexible about skipping calls when there was no agenda Flexibility: When I got accepted to GSoC, after a few days I also got
accepted to a part-time internship that I had applied to before GSoC, while
also managing my last semester in my Bachelor of Computer Science, which was
probably the hardest semester. During our discussion about working capacity,
Danny was very flexible regarding that, with more emphasis on making progress,
which encouraged me to make even more progress. I have also never felt there
are very hard boundaries around my project scope—I felt there was an area to
explore that motivated me to think of and add some side-artifacts to Beam,
e.g., adding Gemini Code Assist for AI code review Proactivity : Danny was very proactive in offering support and help
without originally asking, e.g., making Beam Infra tickets that add API keys
to unblock my work Beam Community: From my first ever contribution to Beam adding FlattenWith and Tee examples to the playground ,
I was welcomed with open arms and felt encouraged to make more contributions.
Also, for their valuable comments on my design documents on the dev mailing list
as well as the PRs Google: I would like to genuinely thank Google for introducing me to open
source in GSoC 2023 and giving me a second chance to interact with Apache Beam through GSoC 2025.
Without it, I probably wouldn’t be here writing this blog post, nor would I have
this fruitful experience What’s Next? I am now focusing on helping move the remaining artifacts in this project scope
from the in-progress state to the merging state. After this, I would love to
keep my contributions alive in Beam Python and Go SDK, to name a few. I would
also love to connect with you all on my LinkedIn and GitHub . References Google Summer of Code Project Listing Original GSoC Proposal GSoC 2025 Tracking Issue
