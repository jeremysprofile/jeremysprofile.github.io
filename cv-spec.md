# Overview
This resume template is made up of 3 areas: a header, a body, and a footer.
This could be made much more modular, with each area being customizable, but right now there are all of two users so I haven't bothered.

## Header
The header has name on top of target role on top of summary on the left, and contact links on the right.
## Body
The body has a sidebar and a main div, each made of a list of [`Grouping`(s)](#grouping).
## Footer
The footer is a div containing a list of [`Grouping`(s)](#grouping).

# YAML Spec

## Schema
```yaml
name: String
logo: Filepath
position: String
summary: Data
contact: List of Data
sidebar: List of Groupings
main: List of Groupings
footer: List of Groupings
```
See [Data](#data), [List](#list), and [Grouping](#grouping).

### String
Can be plaintext or include arbitrary HTML elements (for emphasis, links, abbreviations, etc). Example:
```yaml
text: Jeremy Richards
text: 'I am the <strong>best</strong> at <abbr title="Continuous Integration / Continuous Deployment">CI/CD</abbr>.'
```

### Filepath
Path to image. Images may be any size and dimension. Filepath should start with `/cv/img/` and then the name of the image file (unless you know MkDocs and want images from somewhere else). Example:
```yaml
logo: '/cv/img/j.svg'
```

### List
A YAML list of something. Example:
```yaml
sidebar:
  - Key-value pairs for Grouping 1
  - Key-value pairs for Grouping 2
```

### Grouping
A grouping is a group of experiences, like "Education" for listing your degrees, or "Professional Experience" for listing your jobs (I also use it for "Skills" and listing different skill subgroups like "Languages" or "Platforms").

#### Schema
```yaml
title: String
sections: List of Sections
```

#### Example
```yaml
title: Professional Experience
sections:
  - Section for job 1
  - Section for job 2
```

### Section
A Section is basically one job, education, project, or experience.

#### Schema
```yaml
  title: String
  position: String
  degree: String
  gpa: String
  icon: Filepath
  # set alt and title text for any images used. Very unnecessary.
  icon_title: String
  icon_alt: String
  # Only the first existing key of subtitle, company, or school will be used
  subtitle: String
  company: String
  school: String
  duration: String
  date: String
  data: Data
```

#### Example
```yaml
company: Seagate Technology
icon: /cv/img/seagate-icon.svg
icon_alt: Seagate logo
position: Applications Engineering Intern
date: Jan 2016 - Dec 2016
duration: 1 yr
data: Data for this job
```

### Data
Data is basically the bullet points for a given experience, though it doesn't have to be in bullet point form.

#### Schema
**Each key of Data is optional.**

If Data is confusing, just assume it means "List of String".
```yaml
data:
  # Text to display without bullets or other theme formatting. Is written before bullets if both are specified.
  text: String
  # data will be wrapped in an HTML unordered list
  bullets: List of Data
  # Turns 'text' into a summary element with this object as the details.
  # See https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details
  # If details and bullets are both present, details will expand above bullets.
  details: Data
  # if this is True and details and text are both set, make the details start in expanded display.
  open: Boolean
  # below items should probably only be used in the "Contact" grouping.
  link: URL  # Makes Data a link to the given URL.
  stackoverflow: Stackoverflow
  icon: Filepath
  # set alt and title text for any images used. Very unnecessary.
  icon_title: String
  icon_alt: String

# For convenience, this shortcut is functionally equivalent to only setting data.text.
data: String
# For convenience, this shortcut is functionally equivalent to only setting data.bullets.
data: List of String
```

### Stackoverflow
Displays your StackOverflow data.

#### Schema
```yaml
link: URL  # URL to your profile
# All these Strings are meant to be numbers, but you can write whatever you'd like.
reputation: String
badges:
  gold: String
  silver: String
  bronze: String
```

