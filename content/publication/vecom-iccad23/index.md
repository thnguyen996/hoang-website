---
# Documentation: https://wowchemy.com/docs/managing-content/

title: 'VECOM: Variation-Resilient Encoding and Offset Compensation Schemes for Reliable ReRAM-Based DNN
Accelerator'
subtitle: ''
summary: ''
authors:
- Je-Woo Jang
- <b>Thai-Hoang Nguyen</b>
- Joon-Sung Yang
tags: []
categories: [Emerging Non-Volatile Memory, Variation, ReRAM, Deep Neural Network]
date: '2023-11-20'
lastmod: 2023-11-23T16:35:57+09:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ''
  focal_point: ''
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
publishDate: '2023-12-15T07:35:57.440826Z'
publication_types:
- '1'
 
abstract: "Resistive Random-Access Memory (ReRAM)-based
Processing In-Memory (PIM) Accelerator has emerged as a
promising computing architecture for memory-intensive applications, such as Deep Neural Networks (DNNs). However, due to its
immaturity, ReRAM devices often suffer from various reliability
issues, which hinder the practicality of the PIM architecture
and lead to a severe degradation in DNN accuracy. Among
various reliability issues, device variation and offset current from
High Resistance State (HRS) cell have been considered as major
problems in a ReRAM-based PIM architecture. Due to these
problems, the throughput of the ReRAM-based PIM is reduced
as fewer wordlines are activated. In this paper, we propose
VECOM, a novel approach that includes a variation-resilient
encoding technique and an offset compensation scheme for a
robust ReRAM-based PIM architecture. The first technique (i.e.,
VECOM encoding) is built based on the analysis of the weight
pattern distribution of DNN models, along with the insight into
the ReRAM’s variation property. The second technique, VECOM
offset compensation, tolerates offset current in PIM by mapping
the conductance of each Multi-level Cell (MLC) level added with
a specific offset conductance. Experimental results in various
DNN models and datasets show that the proposed techniques
can increase the throughput of the PIM architecture by up to
9.1 times while saving 50% of energy consumption without any
software overhead. Additionally, VECOM is also found to endure
low R-ratio ReRAM cell (up to 7) with a negligible accuracy drop."

publication: '*Proceedings of the 42nd IEEE/ACM International Conference on Computer-Aided Design (ICCAD) (Accepted)*'
  
# links:
# - name: URL
#   url: https://o365skku-my.sharepoint.com/:b:/g/personal/th_nguyen_o365_skku_edu/EYjKK5DvOY1Cpvsc9E7-1OYB2x5_uM93PM4Sx78NKG3dRQ
# url_poster: 'https://o365skku-my.sharepoint.com/:b:/g/personal/th_nguyen_o365_skku_edu/EeXDkHOPiFtOlNaqLcnOBW0BYjR7oVFSBlRMoAdG50iThQ?e=jVcrWi'

---
