---
title: Publications
type: landing
cms_exclude: true

sections:
  - block: content-collection
    id: preprints
    content:
      title: 'Preprints'
      text: ''
      page_type: publications
      count: 50
      filters:
        author: ''
        category: ''
        tag: ''
        publication_type: 'manuscript'
        exclude_publication_type: ''
        exclude_featured: false
        exclude_future: false
        exclude_past: false
      offset: 0
      order: desc
    design:
      view: citation
      spacing:
        padding: [0, 0, 0, 0]

  - block: content-collection
    id: peer-reviewed
    content:
      title: 'Peer-reviewed'
      text: ''
      page_type: publications
      count: 50
      filters:
        author: ''
        category: ''
        tag: ''
        publication_type: ''
        exclude_publication_type: 'manuscript'
        exclude_featured: false
        exclude_future: false
        exclude_past: false
      offset: 0
      order: desc
    design:
      view: citation
      spacing:
        padding: [0, 0, 0, 0]
---
