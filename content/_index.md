---
title: ''
summary: ''
date: 2026-01-05
type: landing

design:
  spacing: '0'

sections:
  - block: dev-hero
    id: hero
    content:
      username: me
      greeting: "Hi, I'm"
      show_status: true
      show_scroll_indicator: true
      typewriter:
        enable: true
        prefix: "I build"
        strings:
          - "backend systems"
          - "web applications"
          - "developer tools"
        type_speed: 70
        delete_speed: 40
        pause_time: 2500
      cta_buttons:
        - text: View My Work
          url: "#projects"
          icon: arrow-down
        - text: Get In Touch
          url: "#contact"
          icon: envelope
    design:
      style: centered
      avatar_shape: circle
      animations: true
      background:
        color:
          light: "#fafafa"
          dark: "#0a0a0f"
      spacing:
        padding: ["6rem", "0", "4rem", "0"]

  - block: portfolio
    id: projects
    content:
      title: "Featured Projects"
      subtitle: "A selection of my recent work"
      count: 0
      filters:
        folders:
          - projects
      buttons:
        - name: All
          tag: '*'
        - name: Full-Stack
          tag: Full-Stack
        - name: Backend
          tag: Backend
        - name: Frontend
          tag: Frontend
      default_button_index: 0
    design:
      columns: 3
      background:
        color:
          light: "#ffffff"
          dark: "#0d0d12"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]

  - block: tech-stack
    id: skills
    content:
      title: "Tech Stack"
      subtitle: "Technologies I use to build things"
      categories:
        - name: Languages
          items:
            - name: Go
              icon: devicon/go
            - name: Ruby
              icon: devicon/ruby
            - name: TypeScript
              icon: devicon/typescript
            - name: Elixir
              icon: devicon/elixir
        - name: Frameworks
          items:
            - name: Node.js
              icon: devicon/nodejs
            - name: React
              icon: devicon/react
            - name: Phoenix
              icon: devicon/phoenix
            - name: Tailwind CSS
              icon: devicon/tailwindcss
        - name: Infrastructure
          items:
            - name: Docker
              icon: devicon/docker
            - name: PostgreSQL
              icon: devicon/postgresql
            - name: Redis
              icon: devicon/redis
            - name: Linux
              icon: devicon/linux
    design:
      style: grid
      show_levels: false
      background:
        color:
          light: "#f5f5f5"
          dark: "#08080c"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]

  - block: resume-experience
    id: experience
    content:
      title: Experience
      date_format: Jan 2006
      items:
        - title: Senior Software Engineer
          company: Placeholder Company
          company_url: ''
          company_logo: ''
          location: ''
          date_start: '2023-01-01'
          date_end: ''
          description: |2-
            * Placeholder experience entry
            * Replace with your actual experience
        - title: Software Engineer
          company: Previous Company
          company_url: ''
          company_logo: ''
          location: ''
          date_start: '2020-01-01'
          date_end: '2022-12-31'
          description: |2-
            * Placeholder experience entry
            * Replace with your actual experience
    design:
      columns: '1'
      background:
        color:
          light: "#ffffff"
          dark: "#0d0d12"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]

  - block: collection
    id: blog
    content:
      title: Recent Posts
      subtitle: 'Thoughts on development, tech, and more'
      text: ''
      filters:
        folders:
          - blog
        exclude_featured: false
      count: 3
      order: desc
    design:
      view: card
      columns: 3
      background:
        color:
          light: "#f5f5f5"
          dark: "#08080c"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]

  - block: contact-info
    id: contact
    content:
      title: Get In Touch
      subtitle: "Let's connect"
      text: |-
        I'm always interested in hearing about new projects and opportunities.
        Feel free to reach out!
      email: mylan@mylan.io
      autolink: true
    design:
      columns: '1'
      background:
        color:
          light: "#ffffff"
          dark: "#0d0d12"
      spacing:
        padding: ["4rem", "0", "4rem", "0"]
---
