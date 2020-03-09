# Jeremy's wobsite
I don't know what I'm doing.
I'm going to make a website.
It's going to be basic, and I'm gonna enjoy it.

## Goals
* Night mode fight mode
* Resume converts from markdown to styled html automatically
* I link to my automatic transcript or something?

## Problems

I want it to be displayed, but I also want extra stuff.

1. I want a per-page table of contents.
2. I want a global footer.
3. I want a navbar of some kind.

How do I do this?

### Pandoc
I know `pandoc` can convert [GFM](https://github.github.com/gfm/) to HTML.
I just want to add things to this output, but I can't use server-side includes, as that is server code and this is a free, static page from GitHub.

~~[Pelican](https://blog.getpelican.com/) seems to believe it can help.
Literally all I want from Pelican is the ability to add a navbar and footer to each HTML page I get from Pandoc (it *could* manage my CSS, but I'm okay with doing that on my own).~~

Actually, let's just use [`<embed>`](https://stackoverflow.com/a/53675421/5889131). This is really not what it's meant for, but we can abuse it with the knowledge that if we were real people we could just do [server-side includes](https://stackoverflow.com/a/29858653/5889131).

### Flexbox vs Grid
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

I dislike negative margins, so I went with `:last-child` to remove the right margin on my last `<a>` tag.
It works, and reads about as cleanly as I can make it, though it does feel like there should be a better way.
