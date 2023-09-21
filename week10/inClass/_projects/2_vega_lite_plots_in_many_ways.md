---
name: Vega lite plots, multiple ways
tools: [Python, HTML, vega-lite, Altair]
image: assets/pngs/cars.png
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

<!-- these are written in a combo of html and liquid --> 

<div class="left">
{% include elements/button.html link="https://github.com/vega/vega/blob/main/docs/data/cars.json" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/jnaiman/online_cv_public/blob/main/python_notebooks/test_generate_plots.ipynb" text="The Analysis" %}
</div>
