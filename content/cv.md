---
template: cv.html
# Mkdocs really wants this to be a markdown file with YAML frontmatter.
# We'll pretend.
name: "Jeremy Richards"
position: "Software Engineer"
sections:
  Professional Experience:
    - company: Nasdaq
      position: Software Engineer
      date: Sep 2018 - Current
      data:
        bullets:
          - text: "bullet 1"
            details:
              - "detail 1"
            hidden:
              - "detail that won't be displayed #1"
    - company: Seagate Technology
      position: "Applications Engineering Intern"
      date: Jan 2016 - Dec 2016
      data:
        bullets:
          - text: "bullet 2"
            details:
              bullets:
                - "detail 3"
                - "detail 4"
          - text: "content 2"
            bullets:
              - "detail 2"
              - "detail 3"
          - text: "bullet 1"
            details:
              - "detail 1"
Education:
  - school: University of Colorado Boulder
    degree: B.S. Mechanical Engineering, <i>magna cum laude</i>
    GPA: <strong>3.8</strong>
  - school: University of Oklahoma
    degree: B.A. Economics
    minors:
      - Mathematics
      - Psychology
    GPA: <strong>3.96</strong>
---
`info` is a list of `data` objects.
You can specify either `info` or `data` on an object, but not both.
If both are specified, only `info` will be used.

```yaml
info:
  - data:

data:
  # Text to display without bullets or other theme formatting. Is written before bullets if both are specified.
  text: Optional(plaintext or HTML)  # default None
  # Turns 'text' into a summary element with this object as the details.
  # See https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details
  details: Optional(`data`)  # default None
  # if this is True and details and text are both set, make the details start in expanded display.
  open: Optional(boolean)  # default False
  # data will be wrapped in an HTML unordered list
  bullets:
    - Optional(`data`)  # default None

# For convenience, we provide a shortcut that is functionally equivalent to only setting data.text.
data: Optional(plaintext or HTML)
```
