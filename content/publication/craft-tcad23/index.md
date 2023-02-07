---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "CRAFT: Criticality-Aware Fault-Tolerance Enhancement Techniques for Emerging Memories-Based Deep Neural Networks"
authors:
- <b>Thai-Hoang Nguyen</b>
- Muhammad Imran
- Jaehyuk Choi
- Joon-Sung Yang
tags: []
categories: [Emerging Non-Volatile Memory, Stuck-At Fault, Deep Neural Network]
date: '2023-01-01'
lastmod: 2023-01-27T16:35:57+09:00
featured: false
draft: false
doi: "10.1109/TCAD.2023.3240659"

# Schedule page publish date (NOT publication's date).
publishDate: 2023-01-27T23:41:03+09:00

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["2"]

# Publication name and optional abbreviated publication name.
publication: "IEEE Transactions on Computer-Aided Design of Integrated Circuits and Systems
(Accepted)"
# publication_short: "(TCAD)"

abstract: "Deep Neural Networks (DNNs) have emerged as the
most effective programming paradigm for computer vision and
natural language processing applications. With the rapid devel-
opment of DNNs, efficient hardware architectures for deploying
DNN-based applications on edge devices have been extensively
studied. Emerging Non-Volatile Memories (NVMs), with their
better scalability, non-volatility and good read performance,
are found to be promising candidates for deploying DNNs.
However, despite the promise, emerging NVMs often suffer from
reliability issues such as stuck-at faults, which decrease the chip
yield/memory lifetime and severely impact the accuracy of DNNs.
A stuck-at cell can be read but not reprogrammed, thus, stuck-
at faults in NVMs may or may not result in errors depending
on the data to be stored. By reducing the number of errors
caused by stuck-at faults, the reliability of a DNN-based system
can be enhanced. This paper proposes CRAFT, i.e., Criticality-
Aware Fault-Tolerance Enhancement Techniques to enhance the
reliability of NVM-based DNNs in the presence of stuck-at faults.
A data block remapping technique is used to reduce the impact
of stuck-at faults on DNNs accuracy. Additionally, by performing
bit-level criticality analysis on various DNNs, the critical-bit
positions in network parameters that can significantly impact
the accuracy are identified. Based on this analysis, we propose
an encoding method which effectively swaps the critical bit
positions with that of non-critical bits when more errors (due
to stuck-at faults) are present in the critical bits. Experiments
of CRAFT architecture with various DNN models indicate that
the robustness of a DNN against stuck-at faults can be enhanced
by up to 105 times on CIFAR-10 dataset and up to 29 times
on ImageNet dataset with only a minimal amount of storage
overhead i.e., 1.17%. Being orthogonal, CRAFT can be integrated
with existing fault-tolerance schemes to further enhance the
robustness of DNNs against stuck-at faults in NVMs."

# Summary. An optional shortened abstract.
summary: ""

tags: []
categories: []
featured: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

links:
- name: URL
  url: https://ieeexplore.ieee.org/document/10038658
 
url_pdf:
url_code:
url_dataset:
url_poster:
url_project:
url_slides:
url_source:
url_video:

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---
