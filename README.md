<h1>License-Plate-Recognition</h1>
Identify the license plate in an image and recognize its license number.<br>
This is an updated version of one of my other repositories: <a href="https://github.com/anuraggupta29/License_plate_recognition_old">License_plate_recogition_old</a>

<h4>How It Works?</h4>
<ol>
<li>Load the original image.</li>
<li>Grayscale it.</li>
<li>Blur it using bilateral filter.</li>
<li>Automatically generate its canny image basd on median value of pixels.</li>
<li>Find all contours.</li>
<li>Remove contours having small perimeter.</li>
<li>take convex hull of all remaining contours.</li>
<li>For each convex hull, do the following:</li>
<ul><li>Take its approxpolydp.</li>
<li>Try to approximate it as a quadrilateral.</li>
<li>If quadrilateral, check if it's almost a parallelogram</li>
<li>If almost parallelogram, check if the ratio of width/height is similar to a license plate.</li>
<li>Take only those convex hulls which satisfy these conditions.</li></ul>
<li>Do a perspective transform of the convex hulls.</li>
<li>Loop over each convex hull, and try to recognize its text.</li>
<li>The convex hull with the longest text is our license plate.</li>
<li>And the text is our license number.</li>
<ol>
