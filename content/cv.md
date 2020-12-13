---
template: cv.html
# Mkdocs really wants this to be a markdown file with YAML frontmatter.
# We'll pretend, but all the content lives in the "frontmatter".
name: Jeremy Richards
position: Software Engineer
sections:
  Professional Experience:
    - company: Nasdaq
      position: Software Engineer
      date: Sep 2018 - Current
      data:
        - text: 'Took ownership of all new and existing Python applications, including documentation, mentoring, testing, <abbr title="Continuous Integration / Continuous Deployment">CI/CD</abbr>, and DevOps infrastructure'
          details:
            - 'Meticulously documented python development setup process for Windows and Mac users, including package structure, virtual environments, andd test writing for use by other developers'
            - 'Mentored junior developers in Python and programming best practices'
            - 'Set up Nasdaq-internal <a href="https://pypi.org/"><abbr title="Python Package Index">PyPI</abbr></a> server via <a href="https://www.sonatype.com/nexus/repository-pro">Nexus</a>'
          hidden:
            - "Tools: Python 2 and 3, PyCharm, Vim, Poetry, pip, pytest, pre-commit, GitLab-CI"
        - text: 'Diagnosed and resolved time-sensitive production incidents during on-call rotations'
          details:
            - 'Included manual failover, fixing configuration, <abbr title="Root Cause Analysis">RCA</abbr>, providing post-mortem to the team, and writing tickets for any discovered bugs'
        - text: 'Improved <abbr title="Continuous Integration / Continuous Deployment">CI/CD</abbr> pipelines across our application suite by adding: automatic updating to latest internal dependencies, version incrementing, and tagging.'
          details:
             - 'TODO'
        - text: 'Quickly onboarded to adjacent teams as necessary to help meet tight deadlines'
          details: 
             - 'Joined the TradeGuard Reporting team at different points to enable horizontal scaling for trade data processing and to help with <a href="https://www.catnmsplan.com/"><abbr title="Consolidated Audit Trail">CAT</abbr></a> go-live.'
        - text: 'Collaborated on productizing financial message relay application: ported existing setup to <abbr title="Amazon Web Services">AWS</abbr> and Kubernetes; utilized Terraform and Helm for <abbr title="Continuous Integration / Continuous Deployment">CI/CD</abbr>; and improved reliability in server or networking outage scenarios.'
        - text: 'Promoted twice: contractor to Senior Software Developer (E2) to Software Engineer Specialist (E3)'
    - company: Northrop Grumman
      position: Software Engineer
      date: Jun 2017 - Sep 2018
      data:
        - text: 'Created <abbr title="Convolutional Neural Network">CNN</abbr> to classify <abbr title="Code Division Multiple Access">CDMA</abbr> radio signals with noise, including negative <abbr title="Signal-to-Noise Ratio">SNRs'
          bullets:
            - Awarded trade secret bonus for work, which was presented in internal symposium and used in classified space
          open: True
          details:
            - '<abbr title="Convolutional Neural Network">CNNs</abbr> use trained layers to find certain features everywhere in a dataset, rather than in one specific place, meaning target features can be translated or fuzzy and still understood. <abbr title="Code Division Multiple Access">CDMA</abbr> describes methods to share a section of the <abbr title="Radio Frequency">RF</abbr> spectrum with multiple users by encoding data via certain algorithms, such as <a href="https://en.wikipedia.org/wiki/Gold_code">Gold codes</a>. These algorithms are essentially <abbr title="Error Correction Code">ECC</abbr> with huge amounts of redundancy, enabling TODO Radio signals, especially those using Code Division Multiple Access, have patterns associated with the spreading codes use, and it is possible to create a neural network that can detect these patterns, even with some of the bits in the code flipped due to noise.'
            - "Basically, every radio signal has some bandwidth associated with it, it's not all at exactly 8.00 MHz. You can spread the code out to utilize a larger bandwidth at the expense of a lower peak power. You spread your signal out via XORing your signal with a higher frequency spreading code. Spreading a signal has 3 benefits: it means that it's easier for your signal to get around non-uniform interference, you can hide the signal much closer to the noise floor (the level of random radio interference around your part of the spectrum), and with the right spreading code, you can have multiple people use the same part of the spectrum. Allowing multiple users on one part of the spectrum via spreading codes is called Code Dvision Multiple Access (CDMA). Certain sets of binary psuedorandom codes (like Gold codes) have minimal cross-correlation with each other. You can retrieve your signal by taking the dot product of the bandwidth and your spreading code."
          hidden:
            - text: Spread spectrum
              details:
                - "Sending messages over radio frequency (RF) is just sending binary data on a certain frequency via phase, frequency, or amplitude modulation. At some level of abstraction, you can think of it as just sending HIGH or LOW at some bit rate. The bit rate of your signal is proportional to how spread out your signal is in the frequency domain (a low bit rate will result in a signal with a narrow, tall peak, and a high bit rate will yield a shorter, wider curve). The power of the signal you're sending determines how high above the noise floor your signal is, and thus how well others are able to notice and receive it. Signals close to or below the noise floor can still be received if they spread the signal across a wide frequency. There are a bunch of ways to spread a signal."
                - "The spread spectrum I was working on was Direct Sequence Spread Spectrum (DSSS), which uses spreading codes, which are extra phase shifts for each bit of data, sent at a higher rate. Each phase shift in the spreading code is a chip, meaning the spreading code can also be called a chip sequence, and the higher transmission rate is called the chip rate. The chip sequence is multiplied (XOR'd) by the bit sequence - e.g., if your spreading code is 1011 and you want to send 10, you send 0100 1011. Because the chip rate requires sending more data at a higher rate, the signal is spread out further in the frequency domain, so it's hidden closer to or further below the noise floor."
                -  "The information can be decoded by the recipient by multiplying by the same spreading sequence, which effectively provides a huge amount of error correction since multiple chips all encode the same bit. There are a bunch of different spreading codes, useful for different things."
                - "The spreading code I was using was for Code Division Multiple Access (CDMA), which means multiple conversations happening simultaneously in the same frequency band. CDMA is when when all the spreading codes used in one frequency band have very low cross-correlation. Cross-correlation is how related two given spreading codes are, found by multiplying them together - a value at or near zero means there is no cross-correlation. This is useful when multiple conversations are happening, as all but the target conversation will effectively be tuned out by multiplying by the target spreading code. While there are many groups of spreading codes, my tests were on Gold Codes (used by, among other applications, GPS)."
            - text: Convolutional Neural Network
              details:
                - "A convolutional neural network (CNN) is named for the convolutional layers it uses. These layers use a kernel of a specified size (a small contiguous section of the data) and convolve over the input data (matrix multiplication between the trained weights of that kernel and the input values), looking for features of some level of complexity. In the case of images, the standard example is that an initial layer will look for gradients and edges, which intermediate layers will view and interpret into simple shapes, in turn being used to recognize complex shapes, like faces. My task was to apply this to certain types of spreading codes with varying levels of noise."
                - "I used Keras and TensorFlow in Python."
            - "This was exploratory research. I found that in modeled data with added noise, I was able to determine which Gold code was used in a given sample through different clock offsets and negative signal-to-noise ratios. There was no customer for this work and I was taken off the project when Northrop found a non-overhead charge code I could use."
        - text: 'Created <abbr title="Convolutional Neural Network">CNN</abbr> to detect target locations from satellite images'
          details: "92% accuracy, mostly due to a lack of clean data. Was given lat/long data of current and former mines and used the google earth api to get pictures of that area, but the problem was that either the area had re-vegetated or the lat/long didn't have enough precision to accuracy display the mine in the area of the picture."
        - text: 'Used machine learning tools to detect novel inputs on trained <abbr title="Convolutional Neural Network">CNNs</abbr>'
          details: 'Neural networks have a dense layer with only X outputs at the end, one per type (so if you''re training a neural network on cats vs dogs, your final layer will only have 2 outputs, a cat "confidence level" and a dog "confidence level"). However, lower layer neural networks are trained to do feature detection, so it''s possible to have a novel combination of features that is neither a dog nor a cat. The neural net will still only tell you how "much" the image looks like a cat, and how "much" it looks like a dog. It''s possible that the dense layers before the final one have some combination of activations that would be unusual for a picture that is just a dog or a cat. I tried to use isolation forests, support vector machines (SVMs), principal component analysis (PCA), LASSO (variable selection and regularization), and k-nearest neighbor (KNN) analysis. Pulled off the project before I achieved notable results. Northrop was a lot of bouncing between charge codes waiting for my clearance.'
    - company: Seagate Technology
      position: Applications Engineering Intern
      date: Jan 2016 - Dec 2016
      data:
        - text: 'Performed joint testing between Seagate and Fortune 500 companies to qualify hard drives in customer-specific cloud storage systems'
        - text: '<strong>Decreased total qualifications test time 20%</strong>'
          details:
            - 'Wrote tests to be 9% more efficient.'
            - 'The other 11% time reduction was due to increased automation (previously, all tests were kicked off manually during the workday, meaning a test finishing at 6 P.M. would leave the system idle for 14 hours).'
        - text: 'Wrote multi-day Bash scripts to capture performance and error data for populations of hundreds of high-capacity enterprise <abbr title="Hard Disk Drive">HDDs</abbr>'
          details:
            - 'Drives were both <abbr title="Serial Attached SCSI (Small Computer System Interface)">SAS</abbr> and <abbr title="Serial ATA (AT Attachment)">SATA</abbr>, different capacities, and different architectures, including <abbr title="Conventional Magnetic Recoroding">CMR</abbr> and <abbr title="Host-Aware">HA</abbr> <abbr title="Shingled Magnetic Recording">SMR</abbr>. SMR drive tracks overlap so you have to write zones in order; you can''t just rewrite a small part of the zone, you have to write the zone <em>and</em> everything after it. I got to do all the changes necessary to create valid tests for SMR  host-aware drives, and run those qual tests myself.'
        - text: 'Created Python parsers to read data from over 20,000 log files, generate graphs and statistics, and output to Excel'
          details:
            - 'Read in text log files created from our various tests and output data to Excel via <a href="https://pypi.org/project/XlsxWriter/"><code>XlsxWriter</code></a>.'
            - 'Created pivot tables with automatic highlighting, graphs, and summary data output in top workbook with raw data in other workbooks.'
        - text: 'Automated log backup, system setup, and joint qualifications test run on all test systems'
          details:
            - 'The log backup was a cron job to call a service which was just glorified <code>rsync</code> and some logic to put everything into timestamped folders on a secondary server.'
            - 'The system setup and end-to-end test run were slightly fault-tolerant Bash scripts.'

Education:
  - school: University of Colorado Boulder
    degree: B.S. Mechanical Engineering, <i>magna cum laude</i>
    GPA: <strong>3.8</strong>
    data:
      - text: '<a href="http://patft1.uspto.gov/netacgi/nph-Parser?patentnumber=10,429,838"><strong>Co-inventor of Patent No. 10,429,838</strong> for the method of routing drone landings</a>'
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
      - text: 'Placed second of twelve teams in autonomous robot soccer competition. Video of matches <a href="https://www.youtube.com/watch?v=tI_wfxj9qU8">here</a>'
        details: 'Wrote all Arduino (C++) code for: tracking ball & goal via IR sensors, determining relative position on field and estimated ball distance, shooting, and goalie behavior'
        hidden:
         - text: Team designed and assembled Arduino-based robot to play soccer
           details:
             - 'We were given an <a href="https://www.pjrc.com/store/teensy36.html">Arduino offshoot</a>, a maximum size and budget and told to design a roboot capable of scoring goals. The goals and the ball were marked by <abbr title="Infrared">IR</abbr> <abbr title="Light-emitting diode">LEDs</abbr> at specific frequencies. The "field" was white, with black tape for the boundaries and gray tape for the goal zones.'
             - 'We used photodiode "triads" (three photodiodes grouped together at slightly different angles) mounted on servos to sense the ball and goal, tape sensors to view ground color, and four <a href="https://external-preview.redd.it/nnuZFbODO3VGW8P1uZJLeKK03Y9uWf37gGCWrUTuccA.gif?format=mp4&s=b2a1b9b3c52d6cc7dd3aa4601308406b809d97b2">onmiwheels</a> provided movement.'
         - text: 'Wrote all Arduino (C++) code for: tracking ball & goal via IR sensors, determining relative position on field and estimated ball distance, shooting, and goalie behavior'
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
    degree: B.A. Economics
    minors:
      - Mathematics
      - Psychology
    GPA: <strong>3.96</strong>
---
All sections can take a `data` object, as defined below.
```yaml
data:
  # Text to display without bullets or other theme formatting. Is written before bullets if both are specified.
  text: Optional(plaintext or HTML)  # default None
  # Turns 'text' into a summary element with this object as the details.
  # See https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details
  details: Optional(data)  # default None
  # if this is True and details and text are both set, make the details start in expanded display.
  open: Optional(boolean)  # default False
  # data will be wrapped in an HTML unordered list
  bullets:
    - Optional(data)  # default None

# For convenience, we provide a shortcut that is functionally equivalent to only setting data.text.
data: Optional(plaintext or HTML)
# For convenience, we provide a shortcut that is functionally equivalent to only setting data.bullets.
data:
  - Optional(plaintext or HTML)
```


TODO:
  * this:
<!-- This became pure HTML once I wanted too many HTML elements and markdown stopped being sufficient -->
<a href="https://stackexchange.com/users/7783437"><img src="https://stackexchange.com/users/flair/7783437.png" width="208" height="58" alt="profile for jeremysprofile on Stack Exchange" title="profile for jeremysprofile on Stack Exchange"></a>
<!-- TODO why doesn't this display -->
<div data-iframe-width="150" data-iframe-height="270" data-share-badge-id="8e0e38c6-6407-4c4a-8c6d-48ee835a6e67" data-share-badge-host="https://www.youracclaim.com"></div><script type="text/javascript" async src="//cdn.youracclaim.com/assets/utilities/embed.js"></script>
<a href="https://www.youracclaim.com/badges/8e0e38c6-6407-4c4a-8c6d-48ee835a6e67/public_url"><img src="https://images.youracclaim.com/size/340x340/images/1fdcf6a9-de8e-4e35-96b0-e801d8411506/AWS-CloudPractitioner.png" alt="AWS Certified Cloud Practitioner Badge" width=120></a>

Also add `data` to Education.



<!-- vim: filetype=yaml
-->
