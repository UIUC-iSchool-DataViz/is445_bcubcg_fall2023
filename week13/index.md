---
layout: week
visible: true
icon: undraw_playing_fetch_cm19.svg
notitle: true
examples:
  - filename: In Class Jekyll Files
    type: iodide
    title: In class Jekyll materials, Week 13
    description: Updating storage of Idyll files in class
    link: https://github.com/UIUC-iSchool-DataViz/is445_oauoag_spring2023/tree/master/week13/inClass
  - filename: Prep Jekyll Files
    type: iodide
    title: Prep Jekyll materials, Week 13
    description: We'll be building toward a webpage like <a href="https://jnaiman.github.io/online_cv_public/">this</a> today using <a href="https://jekyllrb.com/">Jekyll</a>+<a href="https://altair-viz.github.io/index.html">Altair</a>. 
    link: https://github.com/jnaiman/online_cv_public/blob/main/_example_projects/
  - filename: inClass_week13.ipynb
    type: ipynb
    title: In Class Notebook, Week 13
    description: In class notebook
  - filename: prep_notebook_week13_part1.ipynb
    type: ipynb
    title: Prep Notebook, Week 13, Part 1
    description: Prep notebook for this week
  - filename: prep_notebook_week13_part2.ipynb
    type: ipynb
    title: Prep Notebook, Week 13, Part 2
    description: Prep notebook for this week
data:
  - filename: mobility.csv
    type: dataLink
    title: The Mobility dataset (online)
    description: A dataset of USA "mobility" which (I <b>think</b> comes from a <a href="https://www.census.gov/library/working-papers/2018/adrm/CES-WP-18-40R.html">a large census study from 1989-2015</a>) and is collected in several places <a href="http://www.stat.cmu.edu/~cshalizi/uADA/15/hw/01/mobility.csv">including right here</a>.  Here "mobility" is refering to how easy it is for a person to move up in economic status (<a href="http://www.stat.cmu.edu/~cshalizi/uADA/15/hw/01/hw-01.pdf">more info can be found here</a>) based on factors like parental income, location, race, etc.
    link: https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/mobility.csv
  - filename: building_inventory.csv
    type: dataLink
    title: Buildings dataset
    description: Illinois buildings dataset
    link: https://github.com/UIUC-iSchool-DataViz/is445_data/raw/main/building_inventory.csv
  - filename: corgs_per_country_over_time_columns_2020.csv
    type: dataLink
    title: Corgis per country over time 
    description: This dataset is from the <a href="http://cardiped.net/">Cardigan Archives</a> and <a href="https://github.com/UIUC-iSchool-DataViz/spring2020/blob/master/week12/corg/grabCorgData_subpages.py">scraped using Beautiful Soup in Python</a> and <a href="https://github.com/UIUC-iSchool-DataViz/spring2020/blob/master/week12/corg/calc_corgData.ipynb">further processed in Python</a> into this form.
    link: https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/corgs_per_country_over_time_columns_2020.csv

---

# More with Jekyll+Altair, Intro to SciViz

We talk a little bit about 3D graphics and how it relates to Scientific Visualiazation, and carry on with Jekyll and add in some Altair in Python.

Also, here is a slightly more in-depth explanation of path/ray tracing:

<iframe width="560" height="315" src="https://www.youtube.com/embed/frLwRLS_ZR0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


## Extra files

Full corgi dataset available [here](corg/corgiData_countries_full_2020.json).



## Optional reading list

 1. <a href="https://jekyllrb.com/tutorials/home/">Jekyll Tutorials (hit "Next" to see them at bottom)</a> 
 1. <a href="https://altair-viz.github.io/gallery/index.html">Altair docs</a> - in particular <a href="https://altair-viz.github.io/user_guide/encoding.html#encoding-data-types">Encoding Data Types</a>, <a href="https://altair-viz.github.io/user_guide/internals.html#converting-vega-lite-to-altair">Vegalite-Altair conversions</a>, <a href="https://altair-viz.github.io/user_guide/transform/bin.html#bin-transforms">Binning</a>, <a href="https://altair-viz.github.io/user_guide/transform/filter.html">Filter transforms</a> and <a href="https://altair-viz.github.io/gallery/interactive_cross_highlight.html#interactive-chart-with-cross-highlight">interactive examples</a>
 
 
