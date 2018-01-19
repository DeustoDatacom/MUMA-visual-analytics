---
title: Visual Analytics
subtitle: Communicating data-driven insights<br />through data visualization techniques<br />and useful dashboards
author: Miren Berasategi & Mikel Madina
email: miren.berasategi@deusto.es
theme: deusto
slideNumber: print
...

# 0. Introduction 

## 0.1 Key points

- **Data driven**: as seen in Onieva's and Lorenzo's lectures
- **Insights**: que usen las características gráficas
- **Data visualization techniques**: para obtener las los insights
- **Dashboards**: as *situattion awareness* tools

Tableau Desktop para prácticar


## 0.2 Why use visualizations

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

::: notes

Baina honek ez du esan nahi teknika estatistikoak alde batera utzi behar direnik; batak besteari lagundu behar diote (estatistika tradizionalak bisualizazioari eta alderantziz)

:::

## 0.2 Why use visualizations

![Munzner 2015, p.42](img/munzner-3.1.png){width="600px"}

::: notes

Honek erantzungo lioke "insights" parteari: 

- *Targets* lehenbizi (benetako insighten oinarriak)
- Ondoren *actions*
   - Search (ze target eta non)
   - Query (identifikatu target, baldin eta badago)
   - Azkenik analyze, komunikatu eta datu/modelo berriak sortu

:::

## Tableau

(oinarrizko ezaugarriak)
`data.xls`

Fake data for online marketing tools and Goals

## Tableau 0.1

![Load data](img/tableau_load_data_1080x768.gif){width=700}

## Tableau 0.2

![Metadata view](img/tableau_metadata.gif){width=700}

::: notes

- datuak tableaura kargatu
- "data" bistan bariableak pixkat aztertu
	- sinbolotxoa eta kolorea, tableauk datua nola interpretatu duen jakiteko
	- ze bariable dauden, gero hortik datu kalkulatuak ateratzeko, adibidez irabazitakoa / gastatutakoa oinarrizko KPI modura

:::

# 1. Graphics

## 1.1 Reminder: variable types

- Quantitative
    - Discrete
    - Continuous
- Qualitative
    - Ordinal
    - Nominal

## 1.1 Reminder: variable types <span style="font-size:.8em;display:block">A question of time</span>  {data-transition="none"}

Spatial and time/hour variables are special variable types. **Time variables** are specially complex:

- are there 365 days in every year? 30 days in every month? 24 hours in every day?
- _timezones_ make it even more complex to use hours or time of day

## 1.1 Reminder: variable types <span style="font-size:.8em;display:block">A question of time</span>  {data-transition="none"}

Time may be used as a continuous or as a qualitative variable.

- as a qualitative variable, it has a hierarchy: year > month > (week >) day > hour > minute
- but different hierarchies may be necessary: bimonthly publications, multiple work shifts in a day...

## 1.2 Mapping variables to graphics

![Kirk, 2016 Encodings table [\(source\)](http://book.visualisingdata.com/chapter/chapter-6)](img/6.57.EncodingsTable_preview.png){width="650px"}

::: notes

Grafikoagoa egitea komeniko litzateke

:::

## 1.3 Graphs typology

Variable types and insights (Munzner's "targets") as *ingredients*

[The Data Visualisation Catalogue](https://datavizcatalogue.com/search.html)

::: notes

Si eso Kirken taula sartu, baina taula sortzeko kodea nahiko liosoa da

:::

## Tableau: Show me

![Show me](img/tableau_mostrarme.gif){width=700}

# 2. Provide easier analysis

## 2.1 Change default settings {data-transition="none"}

<figure>

![](img/easieranalysis1.png)

<figcaption style="margin-top:0;">[Data source: Berlin marathon times](https://github.com/hmelberg/berlin-marathon)</figcaption>
</figure>

::: notes

Data: Berlin Marathon

:::

## 2.1 Change default settings {data-transition="none"}

![](img/easieranalysis2.png)

## 2.1 Change default settings {data-transition="none"}

![](img/easieranalysis3.png)

## 2.1 Change default settings {data-transition="none"}

![](img/easieranalysis4.png)

## 2.2 Make simpler graphs

<div style="height:100px;">&nbsp;</div>

>Data-ink is the non-erasable core of the graphic, the non-redundant ink arranged in response to variation in the numbers represented. (Tufte 1983)

## 2.2 Make simpler graphs {data-transition="none"}

A step-by-step example: [Data looks better naked](http://www.darkhorseanalytics.com/blog/data-looks-better-naked)

<div style="margin:auto; width: 70%; height: 0; position: relative; padding-bottom: 90%;"><iframe src="https://speakerdeck.com/player/87bb9f00ec1e01308020727faa1f9e72" style="border: 0; top: 0; left: 0; width: 100%; height: 100%; position: absolute;" allowfullscreen scrolling="no"></iframe></div>

::: notes

Embedeatzea zaila izan da eta diapoak pasatzerakoan izan daiteke efekto arraroren bat egitea

:::

## 2.2 Make simpler graphs {data-transition="none"}

(denborakin ikusteko)

<figure>
<iframe width="560" height="315" src="https://www.youtube.com/embed/X79o46W5plI" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

<figcaption style="margin-top:0;">Nussbaumer, [Declutter Your Data Visualizations](https://www.youtube.com/embed/X79o46W5plI)</figcaption>
</figure>

## 2.3 Highlight observations

[Preattentive attributes](https://www.interaction-design.org/literature/article/preattentive-visual-properties-and-how-to-use-them-in-information-visualization)

![Nussbaumber 2015, p.105](img/nussbaumer-4.4.png){width=650}

## 2.3 Highlight observations {data-transition="none"}

![Nussbaumber, [Do you see it? The importance of contrast when communicating with data [video]](https://www.youtube.com/watch?v=60KiAXbkrl0)](img/nussbaumer-contrast.png){width="700px"}

## 2.4 Add variables (as context)

- Adding preexisting variables (con **mesura**)
- Creating conditional variables from preexisting variables
    - binaries or with few levels are best
    - <span style="font-size:.9em;">example of calculated field or variable: weekend date</span>

![](img/addvariables.png){.fragment}

## 2.5 Add statistical information

<figure style="float:right;width:50%;" class="fragment">
<img src="img/addstatinfo1.png" />

<figcaption>

[source](https://stackoverflow.com/questions/13254441/add-a-horizontal-line-to-plot-and-legend-in-ggplot2)

</figcaption>
</figure>

- statistical summaries
- models

## Tableau: (not so) basic graphs

- [Sparklines (Tufte 2006)](https://www.edwardtufte.com/bboard/q-and-a-fetch-msg?msg_id=0001OR)<br />![](img/sparkline_d3_angular.png){width=300}
- [Bulletgraphs (Few 2007)](https://www.perceptualedge.com/articles/misc/Bullet_Graph_Design_Spec.pdf)<br />![](img/bulletgraph.png){width=300}
- [Heatmaps (Few 2006)](https://www.perceptualedge.com/articles/b-eye/heatmaps.pdf)<br />![](img/heatmap.png){width=300}

::: notes

Nahi badezu bat azaldu eta ondoren tableaun egin, ala hiruak azaldu ta gero hiruak tableaun egin

:::

## Tableau 1.1: Timelines

![Timelines](img/tableau_timeline_1080x768.gif){width=700}

## Tableau 1.2: Bulletgraphs

![Bulletgraphs](img/tablea_bulletgraph_1080x768.gif){width=700}

## Tableau 1.2: Heatmaps

![Heatmaps](img/tablea_heatmap_1080x768.gif){width=700}

## Tableau 2.1: automatic aggregation

![Automatic aggregation](img/tablea_campos_calculados_1_agregaciones_de_tableau1080x768.gif){width=700}

## Tableau 2.2: calculated fields

![Calculated fields](img/tablea_campos_calculados_2_campo_calculado_nivel_linea1080x768.gif){width=700}

## Tableau 2.3: aggregation on calculated fields

![Aggregation on calculated fields](img/tablea_campos_calculados_3_agregaciones_sobre_campos_calculados1080x768.gif){width=700}

## Tableau 2.4: adding KPIs to timelines 1

![Adding KPIs to timelines 1](img/tablea_sparkline_kpi_1_anadir_kpi_basico1080x768.gif){width=700}

## Tableau 2.5: adding KPIs to timelines 2

![Adding KPIs to timelines 2](img/tablea_sparkline_kpi_2_anadir_mas_kpi1080x768.gif){width=700}

# 3. Dashboards

## 3.1 Dashboards for *situation awareness*

Few (liburua, [laburpena 2007](https://www.perceptualedge.com/articles/Whitepapers/Dashboard_Design.pdf))

> The term “dashboard” refers to a single screen information display that is used to monitor what’s going on in some aspect of the business. 

- Perception of own's environment
- Comprehension of it's meaning
- Projection of that understanding into the future

## 3.2 Do's : Principles you should follow

- Use flicker and sound to grab attention
- Encourage active thinking about the data, not just passive reaction to alarms
- Don’t over-automate actions to the point where people become disengaged
- Provide smooth and simple means to respond
- Provide a common picture for the whole team
- Support projections for proactive responses
- Match the mental model

## 3.3 ... and dont's: Design problems you should avoid

- Too much complexity
- Too many alert conditions
- Alerts that cannot be diff erentiated
- Overwhelming visuals
- Distracting visuals
- Inappropriate visual salience
- Mismatch between information and its visual representation
- Indirect expression of measures
- Not enough context

## 3.4 Few's few examples

![](img/few-basic-dashboard.png)

## Dashboards in Tableau

## Tableau 2.1: basic dashboard

![Basic dashboard](img/tablea_dashboard_1_montar_dashboard1080x768.gif){width=700}

## Tableau 2.2: basic formating

![Basic formating](img/tablea_dashboard_2_formateo_basico1080x768.gif){width=700}

## Tableau 2.3: show filters

![Show filters](img/tablea_dashboard_3_mostrar_filtro1080x768.gif){width=700}

## Tableau 2.4: highlight action

![Highlight action](img/tablea_dashboard_4_accion_highlight1080x768.gif){width=700}

## Tableau 2.5: filter action

![Filter action](img/tablea_dashboard_5_accion_filtro1080x768.gif){width=700}

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