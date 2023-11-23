---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "HYDRA: A Hybrid Resistance Drift Resilient Architecture
for Phase Change Memory-Based Neural Network Accelerators"
authors:
- <b>Thai-Hoang Nguyen</b>
- Muhammad Imran
- Jaehyuk Choi
- Joon-Sung Yang
tags: []
categories: [Emerging Non-Volatile Memory, Phase Change Memory, Resistance drift, Deep Neural Network]
date: '2023-11-23'
lastmod: 2023-11-23T16:35:57+09:00
featured: false
draft: false
share: true
# doi: "xxx"

# Schedule page publish date (NOT publication's date).
# publishDate: 2023-01-27T23:41:03+09:00

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["2"]

# Publication name and optional abbreviated publication name.
publication: "IEEE Transactions on Computers (Accepted)"
# publication_short: "(TC)"

abstract: "In-memory Computing (IMC) using Phase Change Memory (PCM) has proven
to be effective for efficient processing of Deep Neural Networks (DNNs).
However, with the use of multi-level cell PCM (MLC-PCM) in NVMs-based
accelerators, errors due to resistance drift in MLC-PCM can severely degrade the
DNNs accuracy. In this paper, an analysis of the impact of resistance drift
errors on accuracy of MLC-PCM based DNN accelerator shows that the drift errors
alone can significantly impact the accuracy. This paper proposes Hydra, which is
a hybrid resistance drift resilient architecture for MLC-PCM based DNN
accelerators which use IMC for efficient computations. Hydra utilizes Tri-level
cell PCM, which has a negligible resistance drift error rate, to store the
critical bits of DNNs parameters and MLC-PCM (4-level cell), which has a higher
error rate (but offers more storage density), for the non-critical bits.
Experimental results on various DNN architectures, configurations and datasets
show that, with the presence of resistance drift errors in PCM, Hydra can
maintain the baseline accuracy of DNNs for up to 1 year (resistance drift is
time-dependent), whereas conventional drift tolerance techniques lead to a
significant accuracy drop in just a few seconds."

# Summary. An optional shortened abstract.
summary: ""

tags: []
categories: []
featured: false

# links:
# - name: URL
#   url: https://ieeexplore.ieee.org/document/10038658
# 
# links:
# - icon_pack: fas
#   icon: scroll
#   name: Preprint
#   url: 'https://arxiv.org/abs/2302.03862'
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
