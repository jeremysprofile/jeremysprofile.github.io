---
template: cv.html
# Mkdocs really wants this to be a markdown file with YAML frontmatter, so we have to pretend by
# putting all our content in the "frontmatter".

logo: '/cv/img/j_light.svg'
name: Lorem Ipsum
position: Software Engineer
summary:
  text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'
  # You can put a 'hidden' key anywhere to keep notes or ideas that won't end up being displayed.
  hidden:
    - 'Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.'

# Icons sourced from https://uxwing.com and https://systemuicons.com/
contact:
  - text: some_email@example.com
    icon: /cv/img/mail.svg
    icon_title: mail
    icon_alt: envelope
    link: mailto:some_email@example.com
  - icon: /cv/img/website.svg
    icon_title: website
    icon_alt: web browser
    text: example.com
    link: https://example.com
  - text: Denver, CO
    icon: /cv/img/location.svg
    icon_title: location
    icon_alt: location pin
  - icon: /cv/img/stackoverflow.svg
    icon_title: Stack Overflow
    icon_alt: Stack Overflow logo
    stackoverflow:
      reputation: 12345
      badges:
        gold: 6
        silver: 7
        bronze: 89
    link: https://stackexchange.com/users/7783437/jeremysprofile?tab=accounts
  - text: github username
    icon: /cv/img/github.svg
    icon_title: git repo
    link: https://github.com/jeremysprofile/jeremysprofile.github.io/tree/resume
  - text: /in/linkedin-username
    icon: /cv/img/linkedin.svg
    icon_title: LinkedIn
    link: https://www.linkedin.com/in/linkedin-username


sidebar:
  - title: Skills
    sections:
      - title: Languages
        data:
          - Python
          - Bash
          - Java
      - title: Platforms
        data:
          - text: Linux
            details:
              - CentOS
              - Alpine
              - Ubuntu
          - Mac
          - Windows
          - Docker
          - Kubernetes
          - AWS
      - title: <abbr title="Infrastructure as Code">IaC</abbr>
        data:
          - Helm
          - Terraform
      - title: Other
        data:
          - Vim
          - Git
          - Kafka
          - Scrum / Agile

main:
  - title: Professional Experience
    sections:
      - company: Company1
        icon: /cv/img/website.svg
        icon_alt: Company1 logo
        position: 'Software Engineer IX'
        date: Sep 2018 - July 2021
        duration: '2 yr 10 mo'
        data:
          - text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. '
            details:
              - 'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. '
            hidden:
              - 'Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. '
          - text: 'Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
          - text: 'Lorem ipsum <a href="https://github.com/jeremysprofile/jeremysprofile.github.io/tree/resume">dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor</a> incididunt ut labore et dolore magna aliqua.'

      - company: Company2
        icon: /cv/img/location.svg
        icon_alt: Company2 logo
        position: SW Engineer I
        date: Jun 2017 - Sep 2018
        duration: 1 yr 3 mo
        data:
          - text: 'Lorem ipsum dolor sit amet, <strong>consectetur</strong> adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. '
            bullets:
              - 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'
            details:
              - 'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
              - 'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
          - text: 'Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.'
            details:
              - 'Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.'
              - 'Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.'
        # You can make hidden as a key on the section to keep bullets you aren't sure you want.
        hidden:
          - text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'
            details:
              - 'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'

      - company: Company3
        icon: /cv/img/location.svg
        icon_alt: Company3 logo
        position: Engineering Intern
        date: Jan 2016 - Dec 2016
        duration: 1 yr
        data:
          - text: 'Lorem <abbr title="ipsum dolor">i.d.</abbr> sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'
          - text: 'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
          - text: 'Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.'

footer:
  - title: Education
    classes: "flex"
    sections:
      - school: University of Schooling
        icon: /cv/img/mail.svg
        icon_alt: US logo
        degree: B.S. Mechanical Engineering
        gpa: 3.8
        data:
          - text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'
          - text: 'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.'
            bullets:
              - 'Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.'

---

<!-- vim: filetype=yaml
  -->
