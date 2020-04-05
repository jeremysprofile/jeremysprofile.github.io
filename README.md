# Jeremy's wobsite
I don't know what I'm doing.
I'm going to make a website.
It's going to be basic, and I'm gonna enjoy it.

## Goals
* Resume and other markdown content to styled html automatically
* I don't want to use a theme - I want a completely custom layout
* Night mode Fight mode
* Knowledge Base articles with:
  * The [GitLab-style](https://docs.gitlab.com/ee/ci/yaml/) scrolling nested headers
  * The [GitLab-style](https://docs.gitlab.com/ee/ci/yaml/) navigation sidebar
* Custom 404, because why not

## Problems
I know *nothing*.

I learned [HTML](./kb/html) and [CSS](./kb/css) for this, but I had to ask a bunch of StackOverflow questions because automatic margin did not make sense.

How do I do all the beautiful things I want?

### Markdown Conversion / Static Site Generator
~~I know `pandoc` can convert [GFM](https://github.github.com/gfm/) to HTML.
I just want to add things to this output, but I can't use server-side includes, as that is server code and this is a free, static page from GitHub.~~

~~[Pelican](https://blog.getpelican.com/) seems to believe it can help.
Literally all I want from Pelican is the ability to add a navbar and footer to each HTML page I get from Pandoc (it *could* manage my CSS, but I'm okay with doing that on my own).~~

~~Actually, let's just use [`<embed>`](https://stackoverflow.com/a/53675421/5889131). This is really not what it's meant for, but we can abuse it with the knowledge that if we were real people we could just do [server-side includes](https://stackoverflow.com/a/29858653/5889131).~~

~~Eventually, I bit the bullet and used [Jekyll](https://jekyllrb.com/docs/github-pages/).
It feels old-school (the design of [their docs pages](https://jekyllrb.com/docs/configuration/markdown/) does not feel modern) but [GitHub still recommends Jekyll](https://help.github.com/en/github/working-with-github-pages).
It does not feel as well documented as I would like.~~

Turns out I'm very fickle on this.
My newest plan is [Nanoc](https://nanoc.ws/about/).
Unlike Jekyll, it's actually used to host some [pretty impressive sites](https://nanoc.ws/about/#why-nanoc), including the docs pages for Prometheus, GitLab, and GitHub (GitHub gets to use it but won't mention it for their GitHub Pages users?).
Also, their docs page is way prettier than Jekyll's.

### Theme
I'm an adult and I demand the ability to make my own theme.
Let's do knowledge.

#### Flexbox vs Grid
CSS [Grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout) ~~feels like~~ is the more modern framework.
There are CSS properties that [were supposed to work on both frameworks](https://github.com/w3c/csswg-drafts/issues/592) but are [only implemented for grid by most browsers](https://caniuse.com/#search=row-gap).

That being said, the main way I want to use grid is the exact opposite of a grid: I want to have "Website - blurb (maybe) - Link1 Link2 ..." and wrap these segments onto multiple lines when appropriate.
I can do this in grid, but I [cannot use `grid-template-columns: repeat(auto-fit, 1fr);`](https://stackoverflow.com/questions/60139602/css-fr-fractional-units-minimum-too-large) to wrap my objects to the next line when the container becomes too small.
Even if this had worked, all my objects would have been the same size, which is probably not the best.
Realistically, Flexbox is better for my use case of auto-wrapping whatever I decide to shove in my header and footer banners.

That being said, I want Flexbox to support my idea syntax of "thing1 thing2 thing3" with some minimum level of space between these elements.
Of course, [multiple people](https://stackoverflow.com/questions/20626685/better-way-to-set-distance-between-flexbox-items) already [asked this question on StackOverflow](https://stackoverflow.com/questions/32984008/how-can-i-set-a-minimum-amount-of-space-between-flexbox-items).
The answers boil down to "use inner `<div>`s between your elements" and "set left and right margins, and then set negative margins on your container".
This is because, while `gap` exists in CSS for use with flexbox, [no one besides Firefox bothered to support it](https://caniuse.com/#feat=flexbox-gap).


### 404

### Nanoc
Here's what I know about Ruby.
I need a different version of Ruby than the `2.3.7` that comes with Mojave, so I need some Ruby version management system.
`rvm` is older, and evidently `rbenv` screws with your shell less.
Also, `rbenv` can be installed with brew, and we're lazy.
```bash
brew install rbenv
```

You can either add this in your `.bashrc`:
```bash
export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init -)"
```

Or just do this on the command line:
```bash
export PATH="$HOME/.rbenv/bin:$PATH"
rbenv init
```

Then you can actually install the ruby version and gem you want:
```bash
rbenv install 2.7.0
rbenv global 2.7.0
rbenv versions  # to verify
gem install nanoc
```
