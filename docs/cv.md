---
template: cv.html
# Mkdocs really wants this to be a markdown file with YAML frontmatter, so we have to pretend by
# putting all our content in the "frontmatter".

logo: '/cv/img/j_light.svg'
name: Jeremy Richards
position: Backend | DevOps
summary:
  text: 'Software engineer focused on fault-tolerance and push-button deployments. Strong technical writer. Proven track record of improving automation, both in <abbr title="Continuous Integration / Continuous Deployment">CI/CD</abbr> and personal workflow.'
  hidden:
    - "CI/CD automation: see Nasdaq gains"
    - "Personal workflow automation: bashrc (brownbag sharing session). proxy login (built own and used another) - documented and shared with team."

# Icons sourced from https://uxwing.com and https://systemuicons.com/
contact:
  - text: me@richards.dev
    icon: /cv/img/mail.svg
    icon_title: mail
    icon_alt: envelope
    link: mailto:jeremy@richards.dev
  - icon: /cv/img/website.svg
    icon_title: website
    icon_alt: web browser
    text: jeremy.richards.dev
    link: https://jeremy.richards.dev
  - text: Denver, CO
    icon: /cv/img/location.svg
    icon_title: location
    icon_alt: location pin
  - icon: /cv/img/stackoverflow.svg
    icon_title: Stack Overflow
    icon_alt: Stack Overflow logo
    stackoverflow:
      reputation: <strong>7.5k</strong>
      badges:
        gold: 3
        silver: 31
        bronze: 83
    link: https://stackexchange.com/users/7783437/jeremysprofile?tab=accounts
  - text: jeremysprofile
    icon: /cv/img/github.svg
    icon_title: git repo
    link: https://github.com/jeremysprofile/jeremysprofile.github.io
  - text: /in/richards-dev
    icon: /cv/img/linkedin.svg
    icon_title: LinkedIn
    link: https://www.linkedin.com/in/richards-dev


sidebar:
  - title: Skills
    sections:
      - title: Languages
        data:
          - Python
          - Bash
          - text: Java
            details:
              - Maven
              - Spring Boot
              - Kotlin
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
          - text: AWS
            details:
              - <a href="https://www.youracclaim.com/badges/8e0e38c6-6407-4c4a-8c6d-48ee835a6e67">Certified Cloud Practioner</a>
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
          - Tutoring


main:
  - title: Professional Experience
    sections:
      - company: Nasdaq
        icon: /cv/img/nasdaq-icon.svg
        icon_alt: Nasdaq logo
        position: 'Contractor → SW Engineer II → SW Engineer III'
        date: Sep 2018 - Current
        duration: '>2 yr 9 mo'
        data:
          - text: 'Took ownership of all Python applications, including architecture, docs, tests, <abbr title="Continuous Integration / Continuous Deployment">CI/CD</abbr>, mentoring, and DevOps infrastructure'
            details:
              - 'Enabled Python 3 migration; set up linters, Nexus <abbr title="Python Package Index">PyPI</abbr> server, and Puppet module; brought all packages up to 80% code coverage'
            hidden:
              - 'Meticulously documented python development setup process for Windows and Mac users, including package structure, virtual environments, and test writing for use by other developers'
              - 'Set up Nasdaq-internal <a href="https://pypi.org/"><abbr title="Python Package Index">PyPI</abbr></a> server via <a href="https://www.sonatype.com/nexus/repository-pro">Nexus</a>'
            tools: "Python 2 and 3, PyCharm, Vim, Poetry, pip, pytest, pre-commit, GitLab-CI"
          - text: 'Added auto-updating internal dependencies, version incrementing, and container tagging to <abbr title="Continuous Integration / Continuous Deployment">CI/CD</abbr> pipelines across application suite'
          - text: 'Repeatedly brought onto understaffed projects, quickly gained domain knowledge and helped meet ambitious deadlines'
          - text: 'Identified and eliminated multiple potential avenues for missing messages in Java <abbr title="Extract, Transform, Load">ETL</abbr> pipeline during port to Kubernetes / <abbr title="Amazon Web Services">AWS</abbr> / Kafka.'
          - text: 'Reduced <abbr title="Amazon Web Services">AWS</abbr> costs via scheduled after-hours shutdown of dev services.'

      - company: Northrop Grumman
        icon: /cv/img/northrop-icon.png
        icon_alt: Northrop Grumman logo
        position: SW Engineer I
        date: Jun 2017 - Sep 2018
        duration: 1 yr 3 mo
        data:
          - text: 'Created neural network to classify <abbr title="Code Division Multiple Access">CDMA</abbr> radio signals at negative <abbr title="Signal-to-Noise Ratios">SNRs</abbr>'
            bullets:
              - 'Awarded trade secret for work, which was presented in internal symposium and used in classified space'
            details:
              - '<abbr title="Code Division Multiple Access">CDMA</abbr> is a way to share bandwidth with cooperating simultaneous users via sets of spreading sequences, which are psuedorandom binary sequences designed to minimally interfere with each other. My goal was to detect usage of a subset of these sequences in a target bandwidth'
              - "This was exploratory research. I found that in modeled data with added noise, I was able to determine which Gold code was used in a given sample through different clock offsets and negative signal-to-noise ratios. There was no customer for this work and I was taken off the project when Northrop found a non-overhead charge code I could use."
          - text: 'Explored machine learning tools to detect novel inputs to trained <abbr title="Convolutional Neural Networks">CNNs</abbr> via intermediate layer activations'
            details:
              - 'A <abbr title="Convolutional Neural Network">CNN</abbr> is pretrained on certain categories and outputs how "likely" a sample is to belong to each category, but cannot determine if a sample belongs to none of the categories. My goal was to leverage the feature detection of the network via tools not requiring pretraining to detect these outlier samples'
              - 'Tested isolation forests, support vector machines, principal component analysis, <abbr title="Least Absolute Shrinkage and Selection Operator">LASSO</abbr>, and k-nearest neighbor analysis'
            hidden:
              - 'Layperson explanation: the last layer in a deep neural network has one neuron per possible classification - a network trained to distinguish images of cats versus images of dogs would have two neurons in the final layer, and whichever neuron is most activated is what the image gets classified as. Intermediate layers will have learned to detect lower-level information about the images (e.g., one neuron could detect the existence of a muzzle, another could detect more dog-like ears). My goal was to see if I could determine if the network had seen a novel image (e.g., a picture of a person) from examining the activations of the intermediate layers, since presumably these images would result in unusual combinations of activations.'
        hidden:
          - text: 'Created convolutional neural network (CNN) to detect mining sites in satellite images'
            details:
              - 'Created training data using Google Earth API and list of GPS coordinates of current (and former) mines'
            hidden:
              - 'Achieved only 92% accuracy due to poor data - some mines had been abandoned and revegetated, and some mine coordinates did not have enough precision to display the mine at sufficient resolution for training'

      - company: Seagate Technology
        icon: /cv/img/seagate-icon.svg
        icon_alt: Seagate logo
        position: Applications Engineering Intern
        date: Jan 2016 - Dec 2016
        duration: 1 yr
        data:
          - text: 'Wrote Bash scripts to test <abbr title="Hard Disk Drive">HDD</abbr> reliability and performance data'
          - text: "Decreased customer's total qualifications test time 20%"
          - text: 'Automated log backup and system setup on all test systems'

footer:
  - title: Education
    classes: "flex"
    sections:
      - school: University of Colorado Boulder
        icon: /cv/img/cu-icon.svg
        icon_alt: CU logo
        degree: B.S. Mechanical Engineering
        gpa: 3.8
        data:
          - text: 'Invented <a href="http://appft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-bool.html&r=1&f=G&l=50&co1=AND&d=PG01&s1=%2210,429,838%22&OS=%2210,429,838%22&RS=%2210,429,838%22">patent 10,429,838</a> for drone landings'
          - text: 'Software team lead in robot soccer competition'
            bullets:
              - 'Team placed second of twelve. <a href="https://www.youtube.com/watch?v=tI_wfxj9qU8">Match videos</a>'

      - school: University of Oklahoma
        icon: /cv/img/ou-icon.svg
        icon_alt: OU logo
        degree: B.A. Economics
        gpa: 3.96
        data:
          - 'Minors: Psychology, Mathematics'

---
This resume template is made up of 3 sections: a header, a body, and a footer.
This could be made much more modular, with each section being customizable, but right now, there is exactly one user, so I haven't bothered.

## Header
The header is a row flexbox with "name / target role / summary" on the left, and contact links on the right.
## Body
The body is a row flexbox with a "sidebar" and a "main", each made of a list of `section`(s).
## Footer
The footer is a div containing a list of `section`(s), where each `section` has `subsection`(s) that are row flexboxes.

## Section
Here is the definition of a `section`:
```yaml
  title:
  subsections:
    - `subsection`
```

## Subsection
Here is the definition of a `subsection`:
```yaml
  # Note: all "string" values can be arbitrary HTML, and are optional.
  # Only the first existing key of title, position, or degree will be used
  title: "string"
  position: "string"
  degree: "string"
  gpa: "string"
  # uses a base directory of /content, where / is the root of the git repo
  icon: filepath/to/image
  # set alt and title text for any images used. Very unnecessary.
  icon_title: "string"
  icon_alt: "string"
  # Only the first existing key of subtitle, company, or school will be used
  subtitle: "string"
  company: "string"
  school: "string"
  duration: "string"
  date: "string"  # prefer format of "mon yyyy - mon yyyy"
  data: `data`
```

## Data
Here is the definition of `data`:
```yaml
data:
  # Text to display without bullets or other theme formatting. Is written before bullets if both are specified.
  text: Optional(plaintext or HTML)  # default None
  # data will be wrapped in an HTML unordered list
  bullets:
    - Optional(data)  # default None
  # Turns 'text' into a summary element with this object as the details.
  # See https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details
  # If details and bullets are both present, details will expand above bullets.
  details: Optional(data)  # default None
  # if this is True and details and text are both set, make the details start in expanded display.
  open: Optional(boolean)  # default False

# For convenience, we provide a shortcut that is functionally equivalent to only setting data.text.
data: Optional(plaintext or HTML)
# For convenience, we provide a shortcut that is functionally equivalent to only setting data.bullets.
data:
  - Optional(plaintext or HTML)
```

<!-- vim: filetype=yaml
  -->
