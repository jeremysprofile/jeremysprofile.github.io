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
