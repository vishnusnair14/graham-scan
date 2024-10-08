## JavaScript Graham's Scan Convex Hull Algorithm

Simple implementation to calculate a convex hull from a given array of x, y coordinates,
the convex hull's in js I found either were a little buggy, or required dependencies on other libraries.
This implementation just takes the x,y coordinates, no other libraries are needed.

These four examples show how to utilise with Google Maps:

[Example 1](http://brian3kb.github.io/graham_scan_js/pages/gmaps_example1.html)
[Example 2](http://brian3kb.github.io/graham_scan_js/pages/gmaps_example2.html)
[Example 3](http://brian3kb.github.io/graham_scan_js/pages/gmaps_example3.html)
[Example 4](http://brian3kb.github.io/graham_scan_js/pages/gmaps_example4.html)

View [GitHub pages](http://brian3kb.github.io/graham_scan_js)

### Building

This produces `graham_scan.min.js`:

	npm install
	grunt build

### Testing

The source is tested with qUnit, tests executed with Google's JS Test Driver.

### Usage

    //Create a new instance.
    var convexHull = new ConvexHullGrahamScan();

    //add points (needs to be done for each point, a foreach loop on the input array can be used.)
    convexHull.addPoint(x, y);

    //getHull() returns the array of points that make up the convex hull.
    var hullPoints = convexHull.getHull();
    
### Algorithm

	GRAHAM_SCAN(Q)
	    Find p0 in Q with minimum y-coordinate (and minimum x-coordinate if there are ties).
	    Sort the remaining points of Q (that is, Q − {p0}) by polar angle in counterclockwise order with respect to p0.
	    TOP [S] = 0                ▷ Lines 3-6 initialize the stack to contain, from bottom to top, first three points.
	    PUSH (p0, S)
	    PUSH (p1, S)
	    PUSH (p2, S)
	    for i = 3 to m             ▷ Perform test for each point p3, ..., pm.
	        do while the angle between NEXT_TO_TOP[S], TOP[S], and pi makes a non-left turn  ▷ remove if not a vertex
	            do POP(S)
	            PUSH (S, pi)
	    return S

### References
* http://en.wikipedia.org/wiki/Graham_scan

### License

MIT License



