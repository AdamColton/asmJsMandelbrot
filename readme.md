## Asm.js Mandelbrot

I wanted to try writing some asm.js (by hand) to understand it's structure. Rendering the Mandelbrot set seemed like a good problem.

I may come back to this at somepoint and add support for Web Workers, using transfer objects it would add a notible performance gain.

Very little code is actually used in computing the set, lines 238-251 and 203-218. It was easier to repeat the algorthm to accomodate the differences in the two shading styles.

The Zebra shading is the most direct approach, and here we choose to highlight the escape bands. Lines 64-129 run a simple smoothing algorithm by averaging each pixel with it's 8 neighbors.

The smoothing algorithm is take directly from the [Wikipedia article](https://en.wikipedia.org/wiki/Mandelbrot_set#Continuous_.28smooth.29_coloring).

All rendering parameters are kept in the URL, so interesting coordinates can be bookmarked or shared. Such as these:
* [Spiral 1](http://projects.adamcolton.net/mandelbrot/#-1.2500245727834485,-1.249900108878368,-0.009867798289101575,-0.009806781804384409,zebra)
* [Spiral 2](http://projects.adamcolton.net/mandelbrot/#-1.249511333230852,-1.2493874126632176,-0.01953525775361511,-0.019474507631591236,zebra)
* [Radial](http://projects.adamcolton.net/mandelbrot/#-0.07804130866976186,-0.07787294874044093,-0.6494512625251992,-0.6493627858748425,smooth)

Have fun!