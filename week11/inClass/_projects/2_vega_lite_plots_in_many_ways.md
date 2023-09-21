---
name: Vega lite plots, multiple ways
tools: [Python, HTML, vega-lite, Altair]
image: assets/pngs/vegalitemanyways.png
description: Vega-lite plots using different methods.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---


# Use Vega-lite in Many Ways in Jekyll

This project will show how to use vega-lite to make plots using different methods, and the vegachart tag from our plugins:

```
<vegachart schema-url="{{ site.baseurl }}/assets/json/cars.json" style="width: 100%"></vegachart>
```

## 1. Directly from vega-editor

<vegachart schema-url="{{ site.baseurl }}/assets/json/vega_editor_plot1.json" style="width: 100%"></vegachart>

<vegachart schema-url="{{ site.baseurl }}/assets/json/vega_editor_plot2.json" style="width: 100%"></vegachart>

## 2. Quick detour with images

We can include our own images that we have stored in 
our `assets/pngs` folder with Markdown:

![a vegalite plot with interactive legend]({{site.baseurl}}/assets/pngs/vegalitemanyways.png)

![example image of vega-lite copied from google search](https://vega.github.io/images/vega-lite.png)

## 3. For real this time, vega-lite from vega-specs to JSON with Altair in Python

<vegachart schema-url="{{ site.baseurl }}/assets/json/chart1.json" style="width: 100%"></vegachart>

Now here is an example of a side-by-side plot (not interactive though):

<vegachart schema-url="{{ site.baseurl }}/assets/json/static_mobility_dashboard.json" style="width: 100%"></vegachart>

I have added some interactivity with a `altair.selection_interval` and `transform_filter`:

<vegachart schema-url="{{ site.baseurl }}/assets/json/dashboard_of_mobility.json" style="width: 100%"></vegachart>

## 4. Start making plots directly from Altair

<vegachart schema-url="{{ site.baseurl }}/assets/json/population_scatter.json" style="width: 100%"></vegachart>

<vegachart schema-url="{{ site.baseurl }}/assets/json/altair_mobility_dashboard.json" style="width: 100%"></vegachart>









<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://github.com/vega/vega/blob/main/docs/data/cars.json" text="The Data" %}
</div>


<div class="right">
{% include elements/button.html link="https://github.com/jnaiman/online_cv_public/blob/main/python_notebooks/test_generate_plots.ipynb" text="The Analysis" %}
</div>

