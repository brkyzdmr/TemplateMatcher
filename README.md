# Template Matcher

In the project, we are locating the defining area as `scale` and `rotation invariant` in the map image using `SIFT` algorithm and return the coordinates of the matched location.

## Why SIFT (Scale Invarient Feature Transform)?
There are tons of feature detection algorithm such as `SIFT`, `SURF`, `FAST`, `BRISK`, `ORB`, etc. Acording to tests, `SIFT` has low error-rate and better accuracy comparing to others. But, it tooks too much time to execute.


## Table of Contents
- [Template Matcher](#template-matcher)
  - [Why SIFT (Scale Invarient Feature Transform)?](#why-sift-scale-invarient-feature-transform)
  - [Table of Contents](#table-of-contents)
  - [Prerequisites](#prerequisites)
  - [Help](#help)
  - [Examples](#examples)
    - [1. Satellite Map Template Matching](#1-satellite-map-template-matching)
    - [2. Star Map Template Matching](#2-star-map-template-matching)
  - [Change Log](#change-log)
  - [Referances](#referances)

## Prerequisites
- Quick install prerequisites
```bash
pip install -r requirements.txt
```

- Package version list
```bash
python 3.7.13
opencv 4.5.5.64 
numpy 1.21.6
matplotlib 3.5.2
```

## Help

```bash 
python template_matcher.py -h

optional arguments:
  -h, --help           show this help message and exit
  --template TEMPLATE  The image to be used as template
  --map MAP            The image to be searched in
  --show               Shows result image
  --save-dir SAVE_DIR  Directory in which you desire to save the result image
```

## Examples

### 1. Satellite Map Template Matching
Finding the exact location and coordinates of a `rotated` part of the satellite map in the satellite map.

```bash
python template_matcher.py --template 'examples\satellite-map\eminonu-satellite-map.jpg' --map 'examples\satellite-map\istanbul-satellite-map.jpg' --save-dir 'examples\satellite-map\output-satellite-map.jpg'
```
**Template:**
<p align="left">
<img src="examples\satellite-map\eminonu-satellite-map.jpg" width="200px"</img><br>
</p>

**Map:**
<p align="left">
<img src="examples\satellite-map\istanbul-satellite-map.jpg" width="500px"</img><br>
</p>

**Result:**

<p align="left">
<img src="examples\satellite-map\output-satellite-map.jpg" width="500px"</img><br>
</p>

**Coordinates:**
```bash
[[[831.315   812.50635]]
 [[794.627   748.854  ]]
 [[728.32965 786.2521 ]]
 [[765.0782  850.3996 ]]]
```

### 2. Star Map Template Matching
Finding the exact location and coordinates of `color overlayed`, `noised`, and `rotated` a part of the star map in the star map.

```bash
python template_matcher.py --template 'examples\star-map\area-on-the-sky.jpg' --map 'examples\star-map\star-map.jpg' --show
```
**Template:**
<p align="left">
<img src="examples\star-map\area-on-the-sky.jpg" width="200px"</img><br>
</p>

**Map:**
<p align="left">
<img src="examples\star-map\star-map.jpg" width="500px"</img><br>
</p>

**Result:**

<p align="left">
<img src="examples\star-map\output-star-map.jpg" width="500px"</img><br>
</p>

**Coordinates:**
```bash
[[[390.81454 742.3058 ]]
 [[513.85657 933.92474]]
 [[755.19464 778.7366 ]]
 [[632.2348  587.18396]]]
```

## Change Log
- Project upgraded ```opencv 3.4.2``` to ```opencv 4.5.5.64```
- Added quick installation for prerequisites

## Referances

1. [Scale-Invariant Feature Transform](https://opencv-python-tutroals.readthedocs.io/en/latest/py_tutorials/py_feature2d/py_sift_intro/py_sift_intro.html)

2. [Feature Matching + Homography to find Objects
](https://opencv-python-tutroals.readthedocs.io/en/latest/py_tutorials/py_feature2d/py_feature_homography/py_feature_homography.html)

3. [Template Matching](https://docs.opencv.org/master/d4/dc6/tutorial_py_template_matching.html)

4. [Histogram Equalization](https://docs.opencv.org/master/d5/daf/tutorial_py_histogram_equalization.html)
5. [A Review on Image Feature Detection and Description](https://www.koreascience.or.kr/article/CFKO201629368424723.pdf)