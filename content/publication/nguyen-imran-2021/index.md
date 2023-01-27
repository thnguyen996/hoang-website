---
# Documentation: https://wowchemy.com/docs/managing-content/

title: Low-Cost and Effective Fault-Tolerance Enhancement Techniques for Emerging
  Memories-Based Deep Neural Networks
subtitle: ''
summary: ''
authors:
- admin
- Muhammad Imran
- Jaehyuk Choi
- Joon-Sung Yang
tags: []
categories: [Emerging Non-Volatile Memory, Stuck-At Fault, Deep Neural Network]
date: '2021-12-01'
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
publishDate: '2023-01-27T07:35:57.186224Z'
publication_types:
- '1'
abstract: "Deep Neural Networks (DNNs) have been found to outperform conventional programming approaches in several applications such as computer vision and natural language processing. Efficient hardware architectures for deploying DNNs on edge devices have been actively studied. Emerging memory technologies with their better scalability, non-volatility, and good read performance are ideal candidates for DNNs which are trained once and deployed over many devices. Emerging memories have also been used in DNNs accelerators for efficient computations of dot-product. However, due to immature manufacturing and limited cell endurance, emerging resistive memories often result in reliability issues like stuck-at faults, which reduce the chip yield and pose a challenge to the accuracy of DNNs. Depending on the state, stuck-at faults may or may not cause error. Fault-tolerance of DNNs can be enhanced by reducing the impact of errors resulting from the stuck-at faults. In this work, we introduce simple and light-weight Intra-block Address remapping and weight encoding techniques to improve the fault-tolerance for DNNs. The proposed schemes effectively work at the network deployment time while preserving the network organization and the original values of the parameters. Experimental results on state-of-the-art DNN models indicate that, with a small storage overhead of just 0.98%, the proposed techniques achieve up to 300× stuck-at faults tolerance capability on Cifar10 dataset and 125× on Imagenet datatset, compared to the baseline DNNs without any fault-tolerance method. By integrating with the existing schemes, the proposed schemes can further enhance the fault resilience of DNNs." 
publication: '*2021 58th ACM/IEEE Design Automation Conference (DAC)*'
doi: 10.1109/dac18074.2021.9586112
links:
- name: URL
  url: https://doi.org/10.1109%2Fdac18074.2021.9586112

url_code: 'https://github.com/thnguyen996/fault-injection'
---
