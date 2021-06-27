# Resume Builder
I made a resume layout.

You're welcome to use it!

## What's it look like?
![Sample resume image](./resume_screenshot.png)

[Link to my resume](https://jeremy.richards.dev/cv/)

## How do I use it?
### Add your content
Add your content to the [`cv.md`](./docs/cv.md) file.
### View your content
#### Install pre-reqs
You need Python3 and `pip`.
```bash
pip install -U mkdocs jinja2
```
#### Serve content
```bash
mkdocs serve
```

### Save your content as a PDF
In your browser, just print to PDF. **Make sure you turn off any page headers/footers and turn on printing background colors and images.**

![Firefox print options](./firefox_print_options.png)
![Chrome print options](./chrome_print_options.png)

#### Publish your content to your static site
If you already use `MkDocs`, you can add your resume to your site by TODO.





NOTE to forgetful future me: I added
```html
<meta http-equiv="refresh" content="0; URL=https://jeremy.richards.dev/cv/" />
```
to `layout/main.html` because my website is not in a state that provides a positive signal to people who might hire me. Just take out the `extraheadings` block when you're ready for the website to work normally again.

## Run on localhost
```bash
mkdocs serve
```
It auto-reloads!

