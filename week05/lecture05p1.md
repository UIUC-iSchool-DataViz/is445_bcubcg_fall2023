---
title: Lecture 5.1 - Grammar of Graphics & bqplot
layout: lecture
description: >-
 We introduce the basics of bqplot & how it relates to grammar of graphics
date: 2023-09-19
---

## Today's Main Topics

 * Traitlets in Python
 * Grammar of Graphics & Imperative vs. Declaritive
 * bqplot


notes:
bqplot!

---

## Where we are: Last week

<img src="../week04/images/data_viz_diagram_week4.png">

notes:
last week we started linking together some visual encodings and programming concepts to build interactivity

---

## Where we are: This week

<img src="images/data_viz_diagram_week05.png">

notes:
today we'll cover a new viz engine called bqplot (we've been using matplotlib as our main viz engine up until this point)

we'll also cover some concepts of grammar of graphics which is a way that many web-based viz engines are layed out

---

## But first!  Some stuff about traitlets in Python!

notes:

**go to in class notebook!**



---

## Next week -- Prof. Jill out of town, "flipped" class for Lab \#4

In particular, I am assuming you have watched the [Part 2 Video](https://mediaspace.illinois.edu/media/t/1_k93hei8q) already before joining the class next week (video on Module page) *and* have looked at the prep notebook in Week 6.

**Extra online office hours with TA Qiuyan Guo (see class Zoom page).**

notes:
**change of modality next week!**

Qiuyan will have extra online hours during class time!


---

<br />
<br />
<br />

# TOPIC 1: Imperative vs. Declaritive Viz Programming Languages

---

![](images/logreas_AFrame_2.gif)

 * "_Declarative_ programming languages ... are rather like logics in that programs declare statements that are known to be true and relationships between these and other statements."
 * "_Imperative_ programming languages ... state what shall be done in given conditions. They start with an initial state and an explicit set of instructions that describe the process that will unfold."

[Reference](http://cfpm.org/~bruce/logreas/logreas_7.html)

notes:
so here are the definitions of declaritive vs. imperative

they are a little nebolous, but for reference we've been using mostly imperative programming for viz

you can think of imperative as a step-by-step reciepe and its usually what you'll run across in programming in Python

---

## Grammar of Graphics for Declaritive Viz

 * Declaritive viz "paints" graphics on a canvas elements common to all visualizations

<!--[](images/GoG.png)-->
<img src="images/GoG.png" width="700"/>


[More info here](https://towardsdatascience.com/a-comprehensive-guide-to-the-grammar-of-graphics-for-effective-visualization-of-multi-dimensional-1f92b4ed4149)

notes:
declarative is more like painting, or linking different viz elements together like data and coordinates

---

## Pandas: Have been using mostly _Imperatively_

 * [pandas.pydata.org](http://pandas.pydata.org/)
 * Support for indexing, multi-indexing
 * Data structures
   * Series
   * DataFrame
   * Panel
 * Groupby, select, aggregation features
 * IO features
   * Reading/writing CSV, HDF5
   * Loading data from remote sources
   
notes:
these are just a few of the ways we've been using Pandas Imperatively

---

<br />
<br />
<br />

# TOPIC 2: Engines - bqplot

---

## Engines

This week we'll be looking at a new visualization engine.

 * `bqplot` - both imperative & declaritive methods

Next few weeks:
 * `vega-lite` - declaritive
 * `Altair` - declaritive (built on `vega-lite`)
 
note:
full disclosure -- bqplot has a matplotlib-like, imperative, programming interface

however, we are going to focus on its declarative interface.  Why?  Because we'll be using other declarative viz engines in the next few weeks so its worth getting some practice here.

---

## bqplot

Our first engine, `bqplot`, is a Jupyter-based interactive plotting system.

It presents two principal interfaces:

1. `pyplot`-like interface, for making the transition from matplotlib easier
```#python
from bqplot import pyplot as bplt
bplt.figure(title='A Figure')
bplt.scatter(x_data, y_data)
bplt.show()
```
1. An object-oriented API for constructing interactive visualizations
```#python
scatter_chart = Scatter(x=x_data, y=y_data, scales={'x': x_sc, 'y': y_sc})
fig = Figure(marks=[scatter_chart], title='A Figure', axes=[x_ax, y_ax])
display(fig)
```

notes:
We will be using the latter far more frequently than the former.

---

## Why bqplot?

 * Has a "matplotlib" style similar to what we've been using thus far
 * Also has an option for the declaritive style of viz software like
 d3.js or tableau
 * Allows us to make NYTimes and 538-style visualizations efficiently, and
 without having to
 learn a lot of javascript

---

## bqplot

Now that we've learned a bit about widgets, we can start to dig into `bqplot`.
`bqplot` is based around traitlets and widget objects; every object you work
with will have traits and may be represented as a widget.

---

## bqplot

Now that we've learned a bit about widgets, we can start to dig into `bqplot`.
`bqplot` is based around traitlets and widget objects; every object you work
with will have traits and may be represented as a widget.

When we use `bqplot` we will be constructing `Figure` objects, which will
contain `marks` and `axes`.  To use these, we will build mark objects (`Bars`,
`Lines`, `Scatter`, `Map`, etc) and describe the relationship between points
using `Scale` objects.

---

## bqplot

Now that we've learned a bit about widgets, we can start to dig into `bqplot`.
`bqplot` is based around traitlets and widget objects; every object you work
with will have traits and may be represented as a widget.

When we use `bqplot` we will be constructing `Figure` objects, which will
contain `marks` and `axes`.  To use these, we will build mark objects (`Bars`,
`Lines`, `Scatter`, `Map`, etc) and describe the relationship between points
using `Scale` objects.

We will be building out these objects and their relationships to develop
interactivity.

---

## bqplot objects: Using Grammar of Graphics

notes:
so, some definitions we'll be using

---

## bqplot objects: Using Grammar of Graphics

 * A `Mark` is some mechanism for displaying data.  For example, we might have
   data that has a set of x and y values, which we can use `Lines` to
   represent.

---

## bqplot objects: Using Grammar of Graphics

 * A `Mark` is some mechanism for displaying data.  For example, we might have
   data that has a set of x and y values, which we can use `Lines` to
   represent.
 * `Scale` objects describe relationships between visual attributes (position)
   and data values.

---

## bqplot objects: Using Grammar of Graphics

 * A `Mark` is some mechanism for displaying data.  For example, we might have
   data that has a set of x and y values, which we can use `Lines` to
   represent.
 * `Scale` objects describe relationships between visual attributes (position)
   and data values.
 * `Axis` objects are where data are placed.

---

## bqplot objects: Using Grammar of Graphics

 * A `Mark` is some mechanism for displaying data.  For example, we might have
   data that has a set of x and y values, which we can use `Lines` to
   represent.
 * `Scale` objects describe relationships between visual attributes (position)
   and data values.
 * `Axis` objects are where data are placed.
 * `Figure` objects contain marks and axes, as well as interaction.

---

## bqplot introduction

Our first example will be a simple lineplot.
```#python
import bqplot
import numpy as np

# 1. data
x = np.arange(100)
y = np.random.random(100) + 5
# 2. scales
x_sc = bqplot.LinearScale()
y_sc = bqplot.LinearScale()
# 3. marks
lines = bqplot.Lines(x = x, y = y, scales = {'x': x_sc, 'y': y_sc})
# 4. sometimes interactive elements are defined around here
# 5. axis
ax_x = bqplot.Axis(scale = x_sc, label = 'X value')
ax_y = bqplot.Axis(scale = y_sc, label = 'Y value', orientation = 'vertical')

# finally: figure
fig = bqplot.Figure(marks = [lines], axes = [ax_x, ax_y])
display(fig)
```

notes:
walk through each line and say this order is pretty usual

---

## Next week -- Prof. Jill out of town, "flipped" class for Lab \#4

In particular, I am assuming you have watched the [Part 2 Video](https://mediaspace.illinois.edu/media/t/1_k93hei8q) already before joining the class next week (video on Module page) *and* have looked at the prep notebook in Week 6.

**Extra online office hours with TA Qiuyan Guo (see class Zoom page).**

notes:
**change of modality next week!**

Qiuyan will have extra online hours during class time!

notes:
just a remidner!

---

# To Python for more interactivity!

---

