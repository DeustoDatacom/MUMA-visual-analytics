---
title: Visual Analytics
subtitle: Communicating data-driven insights through data visualization techniques and useful dashboards
author: Miren Berasategi
email: miren.berasategi@deusto.es
revealjs-url: https://rawgit.com/mberasategi/reveal.js/master/
theme: deusto
slideNumber: print
...

# Introduction 

## Definition(s)

## Why use visualizations

<figure class="fragment"  data-fragment-index="3" style="width:55%; float:right;">
<img src="img/anscombe3.png" alt="Visualizations" />
</figure>

<figure class="fragment"  data-fragment-index="1" style="width:30%; float:left;">
<img src="img/anscombe1.png" alt="Data" style="margin:0 50px;" />
</figure>

<figure class="fragment"  data-fragment-index="2" style="width:40%; float:left;">
<img src="img/anscombe2.png" alt="Summary statistics"  style="margin:0;" />
</figure>

<p style="float:right;width:55%;text-align:center;">
<a href="https://en.wikipedia.org/wiki/Anscombe%27s_quartet">Anscombe's Quartet</a>
</p>

## What to use visualizations for

![Munzner 2015, p.42](img/munzner-3.1.png){width="600px"}

# Graphics

## Reminder: variable types

- Quantitative
    - Discrete
    - Continuous
- Qualitative
    - Ordinal
    - Nominal

## Reminder: variable types <span style="font-size:.8em;display:block">A question of time</span>  {data-transition="none"}

Spatial and time/hour variables are special variable types. **Time variables** are specially complex:

- are there 365 days in every year? 30 days in every month? 24 hours in every day?
- _timezones_ make it even more complex to use hours or time of day

## Reminder: variable types <span style="font-size:.8em;display:block">A question of time</span>  {data-transition="none"}

Time may be used as a continuous or as a qualitative variable.

- as a qualitative variable, it has a hierarchy: year > month > (week >) day > hour > minute
- but different hierarchies may be necessary: bimonthly publications, multiple work shifts in a day...

## Mapping variables to graphics

(Kirk 153-153)

# Provide easier analysis

## Change default settings {data-transition="none"}

![](img/easieranalysis1.png)

## Change default settings {data-transition="none"}

![](img/easieranalysis2.png)

## Change default settings {data-transition="none"}

![](img/easieranalysis3.png)

## Change default settings {data-transition="none"}

![](img/easieranalysis4.png)

## Make simpler graphs

<div style="height:100px;">&nbsp;</div>

>Data-ink is the non-erasable core of the graphic, the non-redundant ink arranged in response to variation in the numbers represented. (Tufte 1983)

## Make simpler graphs {data-transition="none"}

A step-by-step example: [Data looks better naked](http://www.darkhorseanalytics.com/blog/data-looks-better-naked)

<figure class="fragment">
<iframe width="560" height="315" src="https://www.youtube.com/embed/X79o46W5plI" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

<figcaption style="margin-top:0;">Nussbaumer, [Declutter Your Data Visualizations](https://www.youtube.com/embed/X79o46W5plI)</figcaption>
</figure>

## Highlight observations

![Nussbaumber 2015, p.105](img/nussbaumer-4.4.png){width=700}

## Highlight observations {data-transition="none"}

![Nussbaumber, [Do you see it? The importance of contrast when communicating with data [video]](https://www.youtube.com/watch?v=60KiAXbkrl0)](img/nussbaumer-contrast.png){width="700px"}

## Add variables (as context)

- Adding preexisting variables (con **mesura**)
- Creating conditional variables from preexisting variables
    - binaries or with few levels are best
    - <span style="font-size:.9em;">example of calculated field or variable: weekend date</span>

![](img/addvariables.png){.fragment}

## Add statistical information

<figure style="float:right;width:50%;" class="fragment">
<img src="img/addstatinfo1.png" />

<figcaption>

[source](https://stackoverflow.com/questions/13254441/add-a-horizontal-line-to-plot-and-legend-in-ggplot2)

</figcaption>
</figure>


- statistical summaries
- models

# References

---

<div style="text-align:center;">

<h1>Thank you!</h1>

Miren Berasategi<br />
miren.berasategi@deusto.es
</div>

---

<h1>License</h1>

<div style="text-align:center;margin-top:2em;">

![](img/cc/cc.logo.png){height="50px" style="display:inline-block;margin-right:2em;"}
![](img/cc/by.png){height="50px" style="display:inline-block;"}
![](img/cc/sa.png){height="50px" style="display:inline-block;"}

</div>

<p style="font-family:'Frutiger LT Std', Montserrat, Helvetica, Arial, sans-serif; font-size:.4em;font-weight:200;">Copyright &copy; 2018 University of Deusto<br />
This work (except for the quoted images, whose rights are reserved to their owners) is licensed under the Creative Commons “Attribution-ShareAlike” License. To view a copy of this license, visit [http://creativecommons.org/licenses/by-sa/3.0/](http://creativecommons.org/licenses/by-sa/3.0/)</p>

# Test slides

---

First one

## 2nd level heading {data-background="https://static.pexels.com/photos/371633/pexels-photo-371633.jpeg"}

Testing background images 

### 3rd level heading

Second one with content