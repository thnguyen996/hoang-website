---
# Documentation: https://wowchemy.com/docs/managing-content/

title: 'Enhancing the Robustness of eNVMs-Based DNNs using Low-Cost and Efficient Hardware'
subtitle: ''
summary: ''
authors:
- <b>Thai-Hoang Nguyen</b>
- Joon-Sung Yang
tags: []
categories: [Emerging Non-Volatile Memory, Stuck-At Fault, Deep Neural Network]
date: '2023-01-07'
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
publishDate: '2018-11-15T07:35:57.440826Z'
publication_types:
- '1'
 
abstract: "The University of Danang - Danang University of Science and Technology (UD-DUT) is one of the leading
universites in technical training in Central of Vietnam. There are 8 lecture halls with 200 classrooms and the total
area is 240,900 m2. However, it is difficult for students
when they would like to find the shortest to their
classrooms, cafeteria or self-study places.
In order to solve this challenges, we have designed a
self-study management system allowing students to
find a self-study location with available space through
an application on smartphone. Students can use the
GPS function on their smartphone to locate their
position, then choose the place they want to come, the
app will show the shortest path and guide the way. This
application can remind students schedule and time to
return borrowed books to the library. The most
important point is the application can run on both
Android and iOS so that everyone can use our system.
Figure 1 describes a summarized block diagram of
the system. Each self-study place is monitored in
realtime by a node consisting of an embedded
computer Raspberry Pi 3 connected to a camera. The
frame then will be processed using an background
subtraction algorithm [1-3] which is embbeded in the
node’s computer. Information from each node is then
fowared to a gateway using LoRA wireless
communication. The gateway then sends data to the
cloud server by MQTT protocol. A smartphone
application is developed to connect to the server and
get data, then illustrate it in the app [4]. There is a
menu with options to monitor self-study places, use a
 Figure 1: System block diagram
service map or book return reminder. The application
is optimized to run in as many smartphones as possible with small lag as possible.
Experimental results show that when the internet is not stable, there will have a considerable delay in the
application and users will have false information. Further work should solve this problem and to ensure the
stability of the whole system. Feedback from users would help us to improve the user interface of the application.
Deep learning algorithm will be applied to increase the accuracy of human detection at faster speed."

publication: '*17th International Symposium on Advanced Technology (ISAT-17)*'
  
links:
- name: URL
  url: https://www.kogakuin.ac.jp/isat/g8rt6a00000000fm-att/isat17_2018.pdf
url_poster: 'https://o365skku-my.sharepoint.com/:b:/g/personal/th_nguyen_o365_skku_edu/EUOu9a7i5SdPol7YlvDBbhMBdnXChhFVfP54T1L8Jt0QaA?e=ftmlJU'

---
