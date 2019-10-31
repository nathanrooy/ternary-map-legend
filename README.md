# tricolor-map-legend

Need to interpolate between three colors in the shape of a variable density equilateral triangle for a map legend? Look no further! See below for example output:
<p align="center"><img src="example-1.png"></p>
<p align="center"><img src="example-2.png"></p>
<p align="center"><img src="example-3.png"></p>

## Installation
You can either download/clone this repo and use as is, or you can pip install it with the following command:
```sh
pip install git+https://github.com/nathanrooy/tricolor-map-legend
```

## Usage
To create your own color triangle, simply specify three rgb colors, the number of triangles you want along each edge, and an output file name. Since it's an equilateral triangle, this is just a single integer value. The example below is as complicated as it gets.
```python
>>> import tricolor
>>> c1 = [46, 204, 113]         # bottom corner
>>> c2 = [255, 255, 0]          # top left corner
>>> c3 = [52, 152, 219]         # top right
>>> tri_rows = 10               # number of triangles to subdivide each edge
>>> file_name = 'new_triangle'  # output file name
>>> tricolor.tri(tri_rows, c1, c2, c3, file_name)
```
The output of this is an svg file named `new_triangle.svg` which should look like the image below:
<br>
<p align="center"><img width=250, src="new_triangle.svg"></p>

Since SVG files are a vector format making them infinitely scalable, the default triangle edge length to 1000px. To specify a pixel value other than that, add `edge_len` to the function call as seen below:
```python
>>> tricolor.tri(tri_rows, c1, c2, c3, file_name, edge_len=100)
```