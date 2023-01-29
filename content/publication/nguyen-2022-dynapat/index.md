---
# Documentation: https://wowchemy.com/docs/managing-content/

title: 'DynaPAT: A Dynamic Pattern-Aware Encoding Technique for Robust MLC PCM-Based
  Deep Neural Networks'
subtitle: ''
summary: ''
authors:
- Thai-Hoang Nguyen
- Muhammad Imran
- Joon-Sung Yang
tags: []
categories: [Phase Change Memory, Resistance Drift, Deep Neural Network]
date: '2022-01-01'
lastmod: 2023-01-27T16:35:57+09:00
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
publishDate: '2023-01-27T07:35:57.440826Z'
publication_types:
- '1'
 
abstract: "As the effectiveness of Deep Neural Networks (DNNs) is rising over time, so is the need for highly scalable and efficient hardware architectures to capitalize this effectiveness in many practical applications.
Emerging non-volatile Phase Change Memory (PCM) technology has been found to be a promising
candidate for future memory systems due to its better scalability, non-volatility and low
leakage/dynamic power consumption, compared to conventional charged-based memories. Additionally,
with its cell\'s wide resistance span, PCM also has the Flash-like Multi-Level Cell (MLC) capability,
which has enhanced storage density, providing an opportunity for the deployment of data-intensive
applications such as DNNs on resource-constrained edge devices. However, the practical deployment of
MLC PCM is hampered by certain reliability challenges, among which, the resistance drift is
considered to be a critical concern. In a DNN application, the presence of resistance drift in MLC
PCM can cause a severe impact to DNN's accuracy if no drift-error-tolerance technique is utilized. This paper proposes DynaPAT, a low-cost and effective pattern-aware encoding technique to enhance the drift-error-tolerance of MLC PCM-based Deep Neural Networks. DynaPAT has been constructed on the insight into DNN's vulnerability against different data pattern switching. Based on this insight, DynaPAT efficiently maps the most-frequent data pattern in DNN's parameters to the least-drift-prone level of the MLC PCM, thus significantly enhancing the robustness of the system against drift errors. Various experiments on different DNN models and configurations demonstrate the effectiveness of DynaPAT. The experimental results indicate that DynaPAT can achieve up to 500× enhancement in the drift-errors-tolerance capability over the baseline MLC PCM based DNN while requiring only a negligible hardware overhead (below 1% storage overhead). Being orthogonal, DynaPAT can be integrated with existing drift-tolerance schemes for even higher gains in reliability"

publication: '*Proceedings of the 41st IEEE/ACM International Conference on Computer-Aided
  Design (ICCAD)*'
  
links:
- name: URL
  url: https://dl.acm.org/doi/abs/10.1145/3508352.3549400

doi: 10.1145/3508352.3549400
---
