---
# Mkdocs really wants this to be a markdown file with YAML frontmatter.
# We'll pretend.
name: "Jeremy Richards"
position: "Software Engineer"
colors:
  # background and text default to white and black, respectively.
  background:
  text:
  accents:
    primary: 
      background: "#006400"
      text: 
    secondary:
      background: 
      text: 
sections:
  Professional Experience:
    Nasdaq:
      position: "Software Engineer"
      start: "Sep 2018"
      end: "current"
      bullets:
        - bullet: "bullet 1"
          details:
            - "detail 1"
          hidden:
            - "detail that won't be displayed #1"
    Seagate Technology:
      position: "Applications Engineering Intern"
      start: "Jan 2016"
      end: "Dec 2016"
      bullets:
        - bullet: "bullet 1"
          details:
            - "detail 1"
  Education:
    University of Colorado Boulder:
      degree: "B.S. Mechanical Engineering, <i>magna cum laude</i>"
      GPA: "3.8"
    University of Oklahoma:
      degree: "B.A. Economics"
      minors:
        - Mathematics
        - Psychology
      GPA: 3.96
---
# Actual content
