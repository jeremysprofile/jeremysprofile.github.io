# Jeremy's wobsite
I don't know what I'm doing (before starting this in early 2020, I knew no CSS or javascript).
I'm going to make a website.
It's going to be basic, and I'm gonna enjoy it.

## Goals
* [Resume and other markdown content to styled html automatically](#static-site-generator)
* I don't want to use a theme - I want a completely custom layout
* Night mode Fight mode
* [Knowledge Base articles](#knowledge-base) with:
  * The [GitLab-style](https://docs.gitlab.com/ee/ci/yaml/) scrolling nested headers
  * The [GitLab-style](https://docs.gitlab.com/ee/ci/yaml/) navigation sidebar
* Custom 404, because that has to be easy.

### Problems
I know *nothing*.

I knew a bit of [HTML](./kb/html) already and I learned [CSS](./kb/css) for this, but I had to ask a bunch of dumb StackOverflow questions because automatic margin did not make sense.

How do I do all the beautiful things I want?

### Static Site Generator
~~I know `pandoc` can convert [GFM](https://github.github.com/gfm/) to HTML.
I just want to add things to this output, but I can't use server-side includes, as that is server code and this is a free, static page from GitHub.~~

~~[Pelican](https://blog.getpelican.com/) seems to believe it can help.
Literally all I want from Pelican is the ability to add a navbar and footer to each HTML page I get from Pandoc (it *could* manage my CSS, but I'm okay with doing that on my own).~~

~~Actually, let's just use [`<embed>`](https://stackoverflow.com/a/53675421/5889131). This is really not what it's meant for, but we can abuse it with the knowledge that if we were real people we could just do [server-side includes](https://stackoverflow.com/a/29858653/5889131).~~

~~I bit the bullet and used [Jekyll](https://jekyllrb.com/docs/github-pages/).
It feels old-school (the design of [their docs pages](https://jekyllrb.com/docs/configuration/markdown/) does not feel modern) but [GitHub still recommends Jekyll](https://help.github.com/en/github/working-with-github-pages).
It does not feel as well documented as I would like.~~

~~My newest plan is [Nanoc](https://nanoc.ws/).
Unlike Jekyll, it's actually used to host some [pretty impressive sites](https://nanoc.ws/about/#why-nanoc), including the docs pages for Prometheus, GitLab, and GitHub (GitHub gets to use it but won't mention it for their GitHub Pages users?).
Also, their docs page is way prettier than Jekyll's.~~

My current plan is now [MkDocs](https://www.mkdocs.org/), because it's Python, we're using it at my [work](./resume) (TODO fix link), and I avoided touching this projejct for 4 months because that's how little I wanted to deal with Nanoc.
I don't love the fact that it's using [Jinja](https://jinja.palletsprojects.com/) for templating, but given that [Pelican uses Jinja](https://docs.getpelican.com/en/stable/themes.html) and [Jekyll uses Liquid which looks extremely similar at a glance](https://jekyllrb.com/docs/liquid/), I guess I have to accept this is The Way Things are Done<sup>TM</sup> and move on.

#### Flexbox vs Grid
CSS [Grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout) ~~feels like~~ is the more modern framework.
There are CSS properties that [were supposed to work on both frameworks](https://github.com/w3c/csswg-drafts/issues/592) but are [only implemented for grid by most browsers](https://caniuse.com/#search=row-gap).

That being said, the main way I want to use grid is the exact opposite of a grid: I want to have "Website - blurb (maybe) - Link1 Link2 ..." and wrap these segments onto multiple lines when appropriate.
I can do this in grid, but I [cannot use `grid-template-columns: repeat(auto-fit, 1fr);`](https://stackoverflow.com/questions/60139602/css-fr-fractional-units-minimum-too-large) to wrap my objects to the next line when the container becomes too small.
Even if this had worked, all my objects would have been the same size, which is probably not the best.
Realistically, Flexbox is better for my use case of auto-wrapping whatever I decide to shove in my header and footer banners.

That being said, I want Flexbox to support my idea syntax of "thing1 thing2 thing3" with some minimum level of space between these elements.
~~Of course, [multiple people](https://stackoverflow.com/questions/20626685/better-way-to-set-distance-between-flexbox-items) already [asked this question on StackOverflow](https://stackoverflow.com/questions/32984008/how-can-i-set-a-minimum-amount-of-space-between-flexbox-items).
The answers boil down to "use inner `<div>`s between your elements" and "set left and right margins, and then set negative margins on your container".
This is because, while `gap` exists in CSS for use with flexbox, [no one besides Firefox bothered to support it](https://caniuse.com/#feat=flexbox-gap).~~
That's no longer true, [Chrome also supports `gap`, and Safari has it in preview](https://caniuse.com/?search=flexbox-gap), so it's used at least some places on this site (like my resume!).

### Knowledge Base
I really like [GitLab's page formatting](https://docs.gitlab.com/ee/ci/yaml/) with the sidebars and automatic scrolling.
Fortunately, [GitLab uses the MIT license](https://gitlab.com/gitlab-org/gitlab-docs/-/blob/master/LICENSE) (or close enough) so I can swipe with impunity.

Neat.

### GitLab vs GitHub
As far as I can tell, there's very little difference between the two:

* Both keep your source code separate from your build website ([GitHub via separate branch](https://docs.github.com/en/free-pro-team@latest/github/working-with-github-pages/about-github-pages#publishing-sources-for-github-pages-sites), [GitLab via artifact]())
* Both allow for custom 404s ([GitHub](https://docs.github.com/en/free-pro-team@latest/github/working-with-github-pages/creating-a-custom-404-page-for-your-github-pages-site), [GitLab](https://docs.gitlab.com/ee/user/project/pages/introduction.html#custom-error-codes-pages))
* Both allow for push-button HTTPS via [Let's Encrypt](https://letsencrypt.org/) ([GitHub](https://docs.github.com/en/free-pro-team@latest/github/working-with-github-pages/securing-your-github-pages-site-with-https), [GitLab](https://docs.gitlab.com/ee/user/project/pages/custom_domains_ssl_tls_certification/lets_encrypt_integration.html))

Honestly, the only reason I went with GitHub was because I knew about GitHub Pages first and I got it set up and working, while I have some questions abuot how [GitLab would handle HTTPS for my "richards.dev" username](https://docs.gitlab.com/ee/user/project/pages/introduction.html#limitations) and can't tell if [GitLab would honor `/404/index.html` as an alternative to `/404.html`](https://docs.gitlab.com/ee/user/project/pages/introduction.html#custom-error-codes-pages).

# MkDocs
## Install
```bash
unset {HTTP,HTTPS,FTP,NO}_PROXY {http,https,ftp,socks,no}_proxy
pip install mkdocs --index-url https://pypi.python.org/simple
```
[Source](https://mkdocs.readthedocs.io/en/latest/#installation)

## content
This part's pretty easy; you're just writing markdown files.
I already had the markdown content, but I do need some *frontmatter* on them.
This is just the YAML delimiter `---` wrapped around some YAML syntax defining the item variables your layout expects to be present.

## layouts
I used my previous layout, which I poorly iterated through with [this jsfiddle](https://jsfiddle.net/jeremydr2/z9dgeLyc/latest/).
Jekyll used `{{ page.title }}` and `{{ content }}` to add things.
MkDocs is pretty similar, but you have some YAML frontmatter that you define via meta, like `{{ meta.description }}` I think?
## Troubleshooting
### My CSS is only visible on the index!
MkDocs deploys every file like a directory - the file `./contact.md` can be found at `/contact/`, for instance.
This doesn't really matter most of the time, as `/contact` will 301 to `/contact/` automatically, except that you now have a new relative directory.
My original CSS `href` without MkDocs was `href="stylesheet.css"`, but now that all files are directories, this tries to find `site/contact/stylesheet.css` in `site/`, which doesn't exist.

Solution: look at [what the default themes do](https://github.com/mkdocs/mkdocs/blob/1.1.2/mkdocs/themes/mkdocs/base.html#L20), which is
```
href="{{ 'css/bootstrap.min.css'|url }}"
```
Copying that syntax (giving me `href="{{ 'stylesheet.csr'|url }}"`) worked, though to be honest, I don't really know Jinja syntax that well yet.

### My 404 page doesn't work on localhost!
That's expected, I guess. It'll work on a real host.
#### My 404 page doesn't work on a real host!
Yeah, [the MkDocs](https://www.mkdocs.org/user-guide/deploying-your-docs/#404-pages) make it sound like you get a custom 404 page for free.
That's true, but *only with a theme that provides it*.

Since I'm making my own theme, this didn't work; I needed to make a `{{ theme.custom_dir }}/404.html` page and add it as a [static template](https://www.mkdocs.org/user-guide/configuration/#static_templates) (read: is not populated by a `404.md` page).

I was originally against this, since I really wanted my 404 page to be customized, and it made sense to me to customize it via a `404.md` page.
Thee problem with that line of thinking is that MkDocs would create it as `/404/` rather than `/404.html`.
Once I stopped to think about this for a bit, it made sense that they wouldn't add special cases for a `404.md`: the point of markdown is to make writing prose easy, and a 404 page should not be about prose.
If you want a custom 404 page, you'll likely want to customize the style or images, not write a paragraph of text, meaning it is much easier to do in HTML than markdown.

### Nested lists don't work
Python-Markdown (what MkDocs uses) requires 4 spaces for nested lists, not 2 that's supported many other places.
They [closed the issue as WONTFIX](https://github.com/Python-Markdown/markdown/issues/3).

### My website isn't generated on GitHub!
On GitHub, your site must be the only content in its branch.
Mkdocs added a helpful `mkdocs gh-deploy` command to generate your site and push it to the branch of your choice, but I don't like how this uses multiple branches to maintain one version of your website, or how [GitHub's source branch for personal pages was just `master` for 4 years](https://stackoverflow.com/a/39978969/5889131).
After spending a few hours, I was able to figure out how to set up a custom domain on a personal page, which is using `mkdocs gh-deploy` and putting your `CNAME` file under `content/`.
Mkdocs needs more up-to-date docs.

## Run on localhost
```bash
mkdocs serve
```
It auto-reloads!

