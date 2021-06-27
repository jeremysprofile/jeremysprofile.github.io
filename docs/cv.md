---
template: cv.html
# Mkdocs really wants this to be a markdown file with YAML frontmatter.
# We'll pretend, but all the content lives in the "frontmatter".

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
        hidden:
          - Puppet
      - title: Other
        data:
          - Vim
          - Git
          - Kafka
          - Scrum / Agile
          - Tutoring

      # - text: CI/CD
        # open: True
        # details: GitLab-CI
      # - text: Tools
        # open: True
        # details: Vim, Alacritty, Tmux, IntelliJ, PyCharm
      # - text: Misc
        # open: True
        # details: Documentation, Scrum / Agile, Tutoring

      # Barely: HTML, CSS, Jinja, Kotlin, Groovy, SQL, C++
      # Middleware: Kafka
      # - text: Machine Learning
        # open: True
        # details: Keras, TensorFlow, CNNs
      # - text: Containers
        # open: True
        # details: Docker, Kubernetes, Helm


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
            hidden:
               - 'Loaned to adjacent teams to help meet tight deadlines'
               - 'Joined the TradeGuard Reporting team at different points to enable horizontal scaling for trade data processing and to help with <a href="https://www.catnmsplan.com/"><abbr title="Consolidated Audit Trail">CAT</abbr></a> go-live.'
          - text: 'Identified and eliminated multiple potential avenues for missing messages in Java <abbr title="Extract, Transform, Load">ETL</abbr> pipeline during port to Kubernetes / <abbr title="Amazon Web Services">AWS</abbr> / Kafka.'
            hidden: "Previous on-prem implementation would read 1, write 1. Porting to Kafka meant we had to batch our messages, but there were a lot of edge cases involved in batching in terms of duplicate or missed messages. We had to implement Kafka transactions to ensure we accurately tracked message counts and did not lose messages or add duplicates on pod failures. Also had to make sure to split the kafka nodes across EC2 instances and availability zones for redundancy, make sure that topics were created with the right configuration (topics get created on read OR write and we only had configs on the writer microservice)"
          - text: 'Reduced <abbr title="Amazon Web Services">AWS</abbr> costs via scheduled after-hours shutdown of dev services.'
        hidden:
          - text: 'Diagnosed and resolved time-sensitive production incidents during on-call rotations'
            hidden:
              - 'Included manual failover, fixing configuration, <abbr title="Root Cause Analysis">RCA</abbr>, providing post-mortem to the team, and writing tickets for any discovered bugs'

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
            hidden:
              - text: Spread spectrum
                details:
                  - "Sending messages over radio frequency (RF) is just sending binary data on a certain frequency via phase, frequency, or amplitude modulation. At some level of abstraction, you can think of it as just sending HIGH or LOW at some bit rate. The bit rate of your signal is proportional to how spread out your signal is in the frequency domain (a low bit rate will result in a signal with a narrow, tall peak, and a high bit rate will yield a shorter, wider curve). The power of the signal you're sending determines how high above the noise floor your signal is, and thus how well others are able to notice and receive it. Signals close to or below the noise floor can still be received if they spread the signal across a wide frequency. There are a bunch of ways to spread a signal."
                  - "The spread spectrum I was working on was Direct Sequence Spread Spectrum (DSSS), which uses spreading codes, which are extra phase shifts for each bit of data, sent at a higher rate. Each phase shift in the spreading code is a chip, meaning the spreading code can also be called a chip sequence, and the higher transmission rate is called the chip rate. The chip sequence is multiplied (XOR'd) by the bit sequence - e.g., if your spreading code is 1011 and you want to send 10, you send 0100 1011. Because the chip rate requires sending more data at a higher rate, the signal is spread out further in the frequency domain, so it's hidden closer to or further below the noise floor."
                  -  "The information can be decoded by the recipient by multiplying by the same spreading sequence, which effectively provides a huge amount of error correction since multiple chips all encode the same bit. There are a bunch of different spreading codes, useful for different things."
                  - "The spreading code I was using was for Code Division Multiple Access (CDMA), which means multiple conversations happening simultaneously in the same frequency band. CDMA is when when all the spreading codes used in one frequency band have very low cross-correlation. Cross-correlation is how related two given spreading codes are, found by multiplying them together - a value at or near zero means there is no cross-correlation. This is useful when multiple conversations are happening, as all but the target conversation will effectively be tuned out by multiplying by the target spreading code. While there are many groups of spreading codes, my tests were on Gold Codes (used by, among other applications, GPS)."
                  - 'Gold Codes are created by Linear Feedback Shift Registers.'
              - text: Convolutional Neural Network
                details:
                  - "A convolutional neural network (CNN) is named for the convolutional layers it uses. These layers use a kernel of a specified size (a small contiguous section of the data) and convolve over the input data (matrix multiplication between the trained weights of that kernel and the input values), looking for features of some level of complexity. In the case of images, the standard example is that an initial layer will look for gradients and edges, which intermediate layers will view and interpret into simple shapes, in turn being used to recognize complex shapes, like faces. My task was to apply this to certain types of spreading codes with varying levels of noise."
                  - "I used Keras and TensorFlow in Python."
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
            hidden:
              - 'Wrote Bash scripts to run multi-day performance and reliability tests on populations of hundreds of <abbr title="Hard Disk Drives">HDDs</abbr>'
              - 'Created Bash scripts to capture performance and reliability metrics for populations of hundreds of <abbr title="Hard Disk Drives">HDDs</abbr> over multiple days'
              - 'Drives were both <abbr title="Serial Attached SCSI (Small Computer System Interface)">SAS</abbr> and <abbr title="Serial ATA (AT Attachment)">SATA</abbr>, different capacities, and different architectures, including <abbr title="Conventional Magnetic Recording">CMR</abbr> and <abbr title="Host-Aware">HA</abbr> <abbr title="Shingled Magnetic Recording">SMR</abbr>.'
              - text: 'Updated <abbr title="Conventional Magnetic Recording">CMR</abbr>-style tests for <abbr title="Host-Aware">HA</abbr> <abbr title="Shingled Magnetic Recording">SMR</abbr> drives'
                hidden: 'SMR drive tracks overlap so you have to write tracks in order; you can''t just rewrite a small part of the track, you have to rewrite the whole track'
          - text: "Decreased customer's total qualifications test time 20%"
            hidden:
              - 'Wrote tests to be 9% more efficient.'
              - 'The other 11% time reduction was due to increased automation (previously, all tests were kicked off manually during the workday, meaning a test finishing at 6 P.M. would leave the system idle for 14 hours).'

          - text: 'Automated log backup and system setup on all test systems'
            hidden:
              - 'The log backup was a cron job to call a service which was just glorified <code>rsync</code> and some logic to put everything into timestamped folders on a secondary server.'
              - 'The system setup and end-to-end test run were slightly fault-tolerant Bash scripts.'
        hidden:
          - text: 'Automated tests to qualify Seagate <abbr title="Hard Disk Drives">HDDs</abbr> in customer environments'
            hidden: 'Worked with Fortune 100 cloud company as final qualifications gate to ensure interoperability between our drives and their racks'

          - text: 'Created Python parsers to generate graphs, pivot tables, and conditionally-highlighted statistics from >20,000 log files'
            hidden:
              - 'Created pivot tables with automatic highlighting, graphs, and summary data output in top workbook with raw data in other workbooks.'
              - 'Read in text log files created from our various tests and output data to Excel via <a href="https://pypi.org/project/XlsxWriter/"><code>XlsxWriter</code></a>.'

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
            hidden:
              - text: Senior project – drones leave station, get GPS coordinates, determine optimal paths based on obstacles, and fly to targets
                details:
                  - Project team designed drone assigning and tracking app.
                  - text: Wrote Swift code to have drone navigate by vision to specific QR code and land
                    details:
                      - 'Used <a href="https://github.com/zxing/zxing"><code>zxing</code> (Zebra Crossing) pre-existing library</a>.'
                      - 'Computed XYZ offset of drone from pad based on landing pad relative size and position in video and iterated motions to land.'
                  - Our two biggest hurdles were that this was a mechanical engineering course (meaning the timelines and grades were built around design being the largest portion of the project) and that most of Boulder, including the main CU campus, is a no-fly zone for drones, making testing difficult.
                  - In the end, we had individual working pieces, but not a end-to-end success.
                  - Drones could land successfully at landing pads by vision and QR code recognition, plot courses around pre-configured obstacles, and fly to GPS waypoints.
                  - Lack of experience with project planning meant we didn't give ourselves even close to enough time for integration and testing.
          - text: 'Software team lead in robot soccer competition'
            bullets:
              - 'Team placed second of twelve. <a href="https://www.youtube.com/watch?v=tI_wfxj9qU8">Match videos</a>'
            hidden:
              - 'Team designed, built, and programmed robot from off-the-shelf and 3D-printed components'
              - 'Wrote all Arduino (C++) code for tracking ball & goal via IR sensors, determining relative position on field and estimated ball distance, shooting, and goalie behavior'
            hidden:
             - text: Team designed and assembled Arduino-based robot to play soccer
               details:
                 - 'We were given an <a href="https://www.pjrc.com/store/teensy36.html">Arduino offshoot</a>, a maximum size and budget and told to design a robot capable of scoring goals. The goals and the ball were marked by <abbr title="Infrared">IR</abbr> <abbr title="Light-emitting diode">LEDs</abbr> at specific frequencies. The "field" was white, with black tape for the boundaries and gray tape for the goal zones.'
                 - 'We used photodiode "triads" (three photodiodes grouped together at slightly different angles) mounted on servos to sense the ball and goal, tape sensors to view ground color, and four <a href="https://external-preview.redd.it/nnuZFbODO3VGW8P1uZJLeKK03Y9uWf37gGCWrUTuccA.gif?format=mp4&s=b2a1b9b3c52d6cc7dd3aa4601308406b809d97b2">onmiwheels</a> provided movement.'
             - text: 'Wrote all Arduino (C++) code for tracking ball & goal via IR sensors, determining relative position on field and estimated ball distance, shooting, and goalie behavior'
               details:
                 - 'We used parallax to determine relative distance to the ball, and used the relative angle of the goal servos to determine relative location on the field. If we lost track of the ball, we would have the robot engage in goalie behavior, waiting in the goal area for until we found the ball. When attempting to score, we would attempt to line up behind the ball facing directly toward the goal.'
             - text: 'Placed 2nd of 12 teams - <a href="https://www.youtube.com/watch?v=tI_wfxj9qU8">video of competition</a>'
               hidden: >
                 I believe we had the best programmed robot - you can see in the video that we were the only team to actually try to align with the goal when trying to score, while the other teams simply went for the approach of "aim for the ball and hit it", hoping that the fact that the ball was initially ahead of them and toward the target goal would be sufficient.
                 Most of our struggle (and the fact that we got second instead of first) came down to two factors: reflection and multiplexing.
                 During testing, the field wasn''t surrounded by spectators, so there was nothing to reflect the IR of the ball or goals.
                 During the competition, however, the legs of the spectators allowed the IR to bounce and give false positives for ball or goal location.
                 Our other problem was limited speed due to sensor multiplexing. Our design used a single multiplexer to provide the photodiode outputs to a single pin on the Teensy, which greatly simplified wiring at the cost of speed.
                 Because we had to not only detect IR emissions, but also their frequency, we had to wait at minimum for half a period of the frequencies before we could check the next sensor, meaning polling the sensors significantly slowed our loop time.
                 We initially thought this would not be a problem, since our loop was still on the order of tens of milliseconds, but during testing we found that we had to slow our movement speed (both rotation and translation) to a quarter of the maximum to avoid missed signals.
                 Without the multiplexing, we would have been able to average readings and have much more robust data collection.

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

<!-- This became pure HTML once I wanted too many HTML elements and markdown stopped being sufficient -->

<!-- vim: filetype=yaml
  -->
