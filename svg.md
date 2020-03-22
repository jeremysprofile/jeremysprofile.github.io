# SVG
The [Mozilla Dev Docs](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Getting_Started) and [this random website](http://thenewcode.com/28/Making-And-Deploying-SVG-Favicons) showed me how to make SVGs.

I used [this sandbox](https://www.w3schools.com/graphics/tryit.asp?filename=trysvg_myfirst) to try everything since it was the first sandbox I found and I decided figuring out inkscape wasn't worth the effort.

The colors are HTML codes because I'm not creative. The ones that aren't are from [a SuperUser answer](https://superuser.com/a/1206781/809706) describing terminal colors.

I originally made the favicon 40x64 (golden ratio hype) but it turns out browsers only handle square favicons.
I just centered the 40 in a 64 (added 12 to every X value) to make it work.

The golden ratio for a 64 height rectangle specifies a width of 39.554 and a focal point within x in (9.334,15.108) and y in (15.108,24.446), with a center dot at roughly 10.x,17.x.
Center dot for confirmation: `<polygon points="22,47 22,46 23,46 23,47" fill="red" />`

```html
<svg xmlns="http://www.w3.org/2000/svg" width="64" height="64">
	<!-- Darkmode colors -->
	<polygon points="12,0 12,64 52,64 52,0" fill="#282828" />
	<polygon points="40,0 52,0 52,64 40,64 40,56 44,56 44,8 40,8" fill="forestgreen" />
	<polygon points="28,0 36,0 36,8 28,8" fill="#37FF37" />
	<polygon points="12,52 12,64 36,64 36,56 20,56 20,52" fill="#37FF37" />
	<polygon points="12,40 12,48 24,48 24,40" fill="forestgreen" />

	<!-- Lightmode colors -->
	<polygon points="40,0 52,0 52,64 40,64 40,56 44,56 44,8 40,8" fill="darkgreen" />
	<polygon points="28,0 36,0 36,8 28,8" fill="forestgreen" />
	<polygon points="12,52 12,64 36,64 36,56 20,56 20,52" fill="forestgreen" />
	<polygon points="12,40 12,48 24,48 24,40" fill="darkgreen" />

	Sorry, your browser does not support inline SVG.
</svg>
```
