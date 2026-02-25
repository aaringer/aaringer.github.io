---
# Leave the homepage title empty to use the site title
title: ""
date: 2026-02-01
type: landing

design:
  # Default section spacing
  spacing: "6rem"

sections:
  - block: about.avatar
    id: about
    content:
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: admin
      button:
        text: Download CV
        url: https://www.dropbox.com/scl/fi/j64f4wi1w8k58hac0dfzw/AlexaAringer_CV.docx?rlkey=xuq3w1ljqpz9dsm4zum0ja3hc&st=20ktnmxf&dl=0

  - block: collection
    id: featured
    content:
      title: Featured Publications
      filters:
        folders:
          - publication
        featured_only: true
    design:
      view: article-grid
      columns: 2

  - block: collection
    content:
      title: Recent Publications
      text: ""
      filters:
        folders:
          - publication
        exclude_featured: false
    design:
      view: card

  # - block: collection
  #   id: projects
  #   content:
  #     title: Projects
  #     subtitle: ''
  #     text: ''
  #     filters:
  #       folders:
  #         - project
  #   design:
  #     view: card
  #     columns: 2

  # - block: collection
  #   id: blog
  #   content:
  #     title: Recent Blog Posts
  #     subtitle: ''
  #     text: ''
  #     page_type: post
  #     count: 5
  #     filters:
  #       author: ""
  #       category: ""
  #       tag: ""
  #       exclude_featured: false
  #       exclude_future: false
  #       exclude_past: false
  #       publication_type: ""
  #     offset: 0
  #     order: desc
  #   design:
  #     view: compact
  #     spacing:
  #       padding: [0, 0, 0, 0]
  
  # - block: markdown
  #   content:
  #     title: 'Research Overview'
  #     subtitle: ''
  #     text: |-
  #       My research examines how social and psychological factors influence health and well-being across the lifespan. I use a combination of experimental methods, longitudinal surveys, and advanced statistical techniques to understand the complex interplay between personality, social relationships, and health outcomes. My work aims to identify modifiable factors that can promote resilience and positive health behaviors in diverse populations.
  #   design:
  #     columns: '1'
---
