---
# Leave the homepage title empty to use the site title
title: Thai-Hoang Nguyen
date: 2022-10-24
type: landing

sections:
  - block: about.avatar
    id: about
    content:
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: admin
      # Override your bio text from `authors/admin/_index.md`?
      text: 
#  - block: features
#    content:
#      title: Skills
#      items:
#        - name: R
#          description: 90%
#          icon: r-project
#          icon_pack: fab
#        - name: Statistics
#          description: 100%
#          icon: chart-line
#          icon_pack: fas
#        - name: Photography
#          description: 10%
#          icon: camera-retro
#          icon_pack: fas
  - block: experience
    id: experiences
    content:
      title: Experience
      # Date format for experience
      #   Refer to https://wowchemy.com/docs/customization/#date-format
      date_format: Jan 2006
      # Experiences.
      #   Add/remove as many `experience` items below as you like.
      #   Required fields are `title`, `company`, and `date_start`.
      #   Leave `date_end` empty if it's your current employer.
      #   Begin multi-line descriptions with YAML's `|2-` multi-line prefix.
      items:
        - title: BS in Electrical Engineering
          company: Danang University of Science and Technology
          location: Danang, Vietnam
          date_start: '2014-02-01'
          date_end: '2019-02-01'
      #    description: |2-
      #        Responsibilities include:

      #        * Analysing
      #        * Modelling
      #        * Deploying
        - title: Combined MS-PhD in Electrical and Computer Engineering
          company: Sungkyunkwan Univerisity
          location: Suwon, South Korea
          date_start: '2019-03-01'
#          description: Taught electronic engineering and researched semiconductor physics.
    design:
      columns: '2'
  - block: accomplishments
    id: accomplishments
    content:
      # Note: `&shy;` is used to add a 'soft' hyphen in a long heading.
      title: 'Accomplish&shy;ments'
      subtitle:
      # Date format: https://wowchemy.com/docs/customization/#date-format
      date_format: Jan 2006
      # Accomplishments.
      #   Add/remove as many `item` blocks below as you like.
      #   `title`, `organization`, and `date_start` are the required parameters.
      #   Leave other parameters empty if not required.
      #   Begin multi-line descriptions with YAML's `|2-` multi-line prefix.
      items:
        - date_end: ''
          date_start: '2017-01-25'
          description: ''
          organization: Amazon Web Services and BUID-IT Vietnam 
          title: 'The First prize of Amazon EDU Hackathon Coding Competition 2017'
        - date_end: ''
          date_start: '2018-01-01'
          description: ''
          organization: Yokohama National University (YNU)
          title: 'SAKURA exchange program in Science'
        - date_start: '2019-03-01'
          description: ''
          organization: Sungkyunkwan University
          title: 'STEM scholarship for international graduate students'
    design:
      columns: '2'
  - block: collection
    id: publications
    content:
      title: Publications
#      text: |-
#        {{% callout note %}}
#        Quickly discover relevant content by [filtering publications](./publication/).
#        {{% /callout %}}
      filters:
        folders:
          - publication
        exclude_featured: true
    design:
      columns: '2'
      view: citation
  - block: contact
    id: contact
    content:
      title: Contact
      subtitle:
      text: |-
        If you would like to contact me, please send me an email.
      # Contact (add or remove contact options as necessary)
      email: th.nguyen@g.skku.edu
      address:
        street: 50 Yonsei-ro, Sinchon-dong
        city: Seoul
        country: South Korea
      # Automatically link email and phone or display as text?
      autolink: true
    design:
      columns: '2'
---
