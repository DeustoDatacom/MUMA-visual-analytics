---
title: Visual Analytics
subtitle: Communicating data-driven insights<br />through data visualization techniques<br />and useful dashboards
author: <span style="display:block;font-size:.5em;line-height:.7em;">Mikel Madina &</span> Miren Berasategi
email: miren.berasategi@deusto.es
theme: deusto
highlighting-css: .static .author span { display:none !important; }
...

# 0. Introduction 

## 0.1 Key points

- **Data driven**: as seen in previous sessions with Professors Onieva and Lorenzo
- **Insights**: the capacity to gain an accurate and deep understanding of something _through_
- **Data visualization techniques**: to take the user from data to insight
- **Dashboards**: as *situation awareness* tools

Tableau Desktop to practice

## Section outline

0. Introduction: the _why_ and the _what for_ of visualization 
1. Graphs: some reminders, idioms to map variables to graphs
2. Promote insight: by adding meaningful modifications to graphs
3. Dashboards: situation awareness, dos and don'ts
4. Epilogue

Practice: build a simple dashboard with online marketing campaign data


## 0.2 Why use visualization

- Sight is our most developed sense
- The visual system provides a very high-bandwidth channel to our brains
- A significant amount of visual information processing occurs in parallel at the preconscious level
- The human brain is _trained_ to identify visual patterns
- Summary statistics have the intrinsic limitation of data loss

::: notes 

Implications of visual perception relevant to visualization design on next section

:::

## 0.2 Why use visualization

<figure class="fragment"  data-fragment-index="3" style="width:55%; float:right;">
<img src="img/anscombe3.png" alt="Visualizations" />
</figure>

<figure class="fragment"  data-fragment-index="2" style="width:30%; float:left;">
<img src="img/anscombe1.png" alt="Data" style="margin:0 50px;" />
</figure>

<figure class="fragment"  data-fragment-index="1" style="width:40%; float:left;">
<img src="img/anscombe2.png" alt="Summary statistics"  style="margin:0;" />
</figure>

<p style="float:right;width:55%;text-align:center;">
<a href="https://en.wikipedia.org/wiki/Anscombe%27s_quartet">Anscombe's Quartet</a>
</p>

::: notes

Traditional summary statistics can be misleading. These datasets share almost identical mean, variance, correlation and linear regression lines.

1. Shows _normal_ distribution
2. There is correlation, but it's not linear
3. There is correlation, it IS LINEAR, but different from what emerged from the data
4. No relationship whatsoever. Outlier is enough for _apparent_ correlation

**Bottom line**: summary statistics, although very sensitive to outliers, are important, but plotting the data (visualization) is also a necessary step during the first stages of the data analytics process, before making any assumptions. 

Munzner 2014 p.8

:::

## 0.3 What to use visualization for

![Munzner 2014, p.42](img/munzner-3.1.png){width="600px"}

::: notes

What are we using visualization for?

Important to answer to this question in an **abstract form**, instead of domain-specific.

We are going to divide into

- _targets_ = nouns
- _actions_ = verbs 

<!--
Honek erantzungo lioke "insights" parteari: 

- *Targets* lehenbizi (benetako insighten oinarriak)
- Ondoren *actions*
   - Search (ze target eta non)
   - Query (identifikatu target, baldin eta badago)
   - Azkenik analyze, komunikatu eta datu/modelo berriak sortu
-->

:::

## 0.3 What to use visualization for

![Munzner 2014, p.56](img/munzner-3.6-wide.png){width="725"}

::: notes

- Very broadly relevant for all kinds of data: trends, outliers, features
- One attribute/variable: find an individual value, distribution of all values, find extremes
- Many attributes: dependency, correlation, similarity
- The rest (network/spatial) are specific to certain types of datasets

The abstract task of understanding **trends, outliers, distributions and correlations** are extremely common reasons to use data visualization.

:::

## 0.3 What to use visualization for

![Munzner 2014, p.46](img/munzner-3.2-wide.png)

::: notes

- Search for an element of interest (based on knowledge of identity & location)
  + lookup: humans in tree vis of species of mammals
  + locate: where are rabbits? lagomorphs -- not rodents
  + browse: when users don't know exactly what they're looking for but have an idea of characteristics
  + explore: not sure of either one
- Once a target or set of targets is identified, query those at one of 3 scopes (progression from one to many to all targets)
  + identify (US election map example)
  + compare, more difficult, requires more sophisticated idioms
  + summarize = overview (extremely common)
- Analyze data:
  + consume (most common use case): discover, present (known info, i.e. insights), enjoy (for the fun of it)
  + produce: annotate, record (capture steps), derive (produce new data elements)

:::

## 0.3 What to use visualization for

<blockquote style="width:90% !important; font-size:.9em; margin-top:2em;">
  <p style="margin:0;">There is a **strong relationship** between the form of the data (the attribute/variable and dataset types) and what kinds of vis[ualization] idioms are effective at displaying it. (...) Don't just draw what you are given; decide what the right thing to show is, create it with a series of **transformations** from the original database, and draw that!</p>
</blockquote>

<figure><figcaption style="text-align:right;">Munzner 2014, p.50</figcaption></figure>

::: notes

Transformation (=derive) may be required depending on the desired type of insight -- derived attributes/variables extend the original dataset

- in some cases, the same data with a change of type (temperature _vs._ "hot" or "cold")
- in other cases, access to additional info is required (geo: city name to lat/lon)
- created through arithmetic, logaritmic or statistial operations (i.e. diff field)

:::

## 0.3 What to use visualization for

![Derived attributes can be directly visually encoded. Munzner 2014, p.52](img/munzner-3.5.png)

## Practice: meet our sample data

<div class="right" style="width:45%; float:right;">

![](img/data-excel.png)

</div>

<div class="left" style="width:45%; float:left;">
Download and open `data.xls`: fake data for online marketing goals and tools

<span style="font-size:.8em;">
from Google Drive or [`http://mrn.bz/MUMA2018data`](http://mrn.bz/MUMA2018data)
</span>
</div>

::: notes

Shows results of campaigns in three different sources, per quarters (trimester). Money spent in each source, number of visits got from that campaign, income generated, and goal income for each source.

Takes for granted many things, such as validity/reasonability of goals, of spent money per goal...

:::

## Tableau Software

<div class="right" style="width:75%; float:right;">

![Tableau Software](img/tableau/tableau-getinsightsfast.gif){width=750}

</div>

<div class="left" style="width:23%; float:left;">

![](img/tableau/tableau-logo.png)

</div>

## Tableau

1. Load data
2. Explore the `Data Source` tab

See the subtle blue/green colour of the variable type icon? Take notice, it is important:

<blockquote style="width:90%; font-size:.9em;">
  <p style="margin:0 !important; line-height:1em;">Understanding the difference between the blue and green items in Tableau is (IMHO) the single most important piece of understanding necessary to make Tableau function well. </p>
</blockquote>

<figure>
  <figcaption style="text-align:right;">
Tom Brown, [Blue things and Green things](https://www.theinformationlab.co.uk/2011/09/23/blue-things-and-green-things/)
  </figcaption>
</figure>

::: notes

- Possible to _merge_ more sources (or **Connections**), only one for our practice -- might require to define `New Union` to determine how merge takes place
- Shows the only sheet in the file, may be more
- `Connection > Live/Extract`, first one allows to modify source file and update work accordingly

Interprets the `source` field as `Abc`, rest as `#` (well done). Only, we would rather improve the `quarter` interpretation as `Date` instead of `Number`

Green & blue: **blue fields** are discrete, **green fields** are continuous. We'll see implications of this later on. For now, it's all good

Rename, hide... fields

The Excel > Tableau convert is quite straightforward (does a good job), more complex sources may require more manipulation at this point

This screen allows to preview how Tableau is interpreting our dataset: we are not allowed to change values, only variable interpretations

The source file (`data.xls`) is never modified

:::

<!--
![Load data](img/tableau_load_data_1080x768.gif){width=700}


## Tableau 0.2

![Metadata view](img/tableau_metadata.gif){width=700}

::: notes

- datuak tableaura kargatu
- "data" bistan bariableak pixkat aztertu
	- sinbolotxoa eta kolorea, tableauk datua nola interpretatu duen jakiteko
	- ze bariable dauden, gero hortik datu kalkulatuak ateratzeko, adibidez irabazitakoa / gastatutakoa oinarrizko KPI modura

:::

-->

# 1. Graphs

---

## Section outline

1. Reminder: variable types
2. Mapping variables to graphs
  - Marks
  - Channels, channel types
  - Using marks and channels
3. So, which graph?

Practice: explore dimensions, measures and graph types in Tableau

---

<figure class="fragment" style="float:right;width:600px;">
  <img src="img/graph-ex-bars.png" />
</figure>

<figure class="fragment" style="float:right;width:500px;clear:right;">
  <img src="img/graph-ex-map.png" />
</figure>

<figure class="fragment" style="float:right;width:500px;clear:right;">
?
</figure>

![](img/graph-ex-data.png){width=200}

::: notes

Dataset showing town name and amount of subsidies (funds) received in a given year. How do you think we could visualize this?

- visualization requires _mapping_ or _translation_ from _data_ to _visual language_ (idioms)
- this can be done in many ways

1. subsidy amount = bar height, color irrelevant
2. to show in map **transformation is required** (not possible directly)
  - color IS relevant (subsidy amount = color saturation)
  - comparison is more difficult: not _ordered_ (althoug not impossible)
  - allows for more direct insight (if context - knowledge of the area): Vitoria-Gasteiz not getting the higher amount
3. anything else? (i.e. pie chart, treemap...)

:::

## 1.1 Reminder: variable types

<div class="fragment" style="float:right;width:60%;font-family:'Frutiger LT Std', Montserrat, sans-serif;font-size:.5em;font-weight:200;">

<b>A question of time</b>

Spatial and time/hour variables are special variable types. **Time variables** are specially complex:

- are there 365 days in every year? 30 days in every month? 24 hours in every day?
- _timezones_ make it even more complex to use hours or time of day

Time may be used as a continuous or as a qualitative variable.

- as a qualitative variable, it has a hierarchy: year > month > (week >) day > hour > minute
- but different hierarchies may be necessary: bimonthly publications, multiple work shifts in a day...

</div>

- Quantitative
    - Continuous
    - Discrete
- Qualitative
    - Categorical
    - Ordinal
- Special types
  + time
  + space
  + ...

::: notes

- continuous variables can take on infinite/uncountable values (time, real numbers)
- discrete variables can take a finite/countable number of values (periods of time, integers)

- categorical/nominal: two or more categories, any order (gender, political party...). Cannot be quantified, do not allow arithmetic operations, cannot be assigned any order
- ordinal: allows for rank order (1st, 2nd, 3rd...). Can be dichotomous (yes/no, right/wrong, sick/healthy...) or non-dichotomous (spectrum of values:  completely agree, mostly agree, mostly disagree, completely disagree)

:::

## 1.2 Mapping variables to graphs

<!--

![Kirk, 2016 Encodings table [\(source\)](http://book.visualisingdata.com/chapter/chapter-6)](img/6.57.EncodingsTable_preview.png){width="650px"}

::: notes

Grafikoagoa egitea komeniko litzateke

:::

-->

<div style="height: 3em;"></div>

Understanding **marks and channels** provides the building blocks for analyzing visual encodings (Munzner 2014, p.95)

---

### 1.2.1 Marks

<div style="height: 1em;"></div>

A **mark** is a basic graphical element in an image

![Marks are geometric primitives (Munzner 2014, p.96)](img/munzner-5.2.png)

::: notes

- a zero-dimensional (0D) mark is a point
- a one-dimensional (1D) mark is a line
- a two-dimensional (2D) mark is an area
- a three-dimensional (3D) mark is possible but not frequently used (will see why)

:::

---

### 1.2.2 Channels

A visual **channel** is a way to control the appearance of marks

![Visual channels control the appearance of marks (Munzner 2014, p.96)](img/munzner-5.3.png){width=500}

::: notes

- spatial position (_where_)
- color, with three distinct aspects: hue, saturation, luminance (more in the next slide)
- size, one for each added dimension: length 1D, area 2D, volume 3D
- angle/tilt/slope
- others are shape, curvature

:::

---

### 1.2.2 Channels

<div style="height: 1em;"></div>

**One and only one** attribute/variable should be used per channel.

Multiple channels per attribute are possible (**redundant encoding**), but this approach has limitations.

::: notes

more channels are "used up", so less attributes can be encoded in total, 

BUT the attributes that are shown will be very easily perceived (i.e. color of political party for bar charts)

:::

---

### 1.2.2 Channels

<div style="height: 1em;"></div>

The **size** and **shape** channels cannot be used on all types of marks, but most combinations are still possible:

- lines have two _size channels_: length + width
- points refer to location but can be _size_ and _shape_ coded

::: notes

Area marks cannot typically be size or shape coded: state or country already has a certain size and shape

- lines: if length is _taken_ by a variable, it can't be used for another one, but width can be used to size code. They can be made wider on an individual basis to encode an additional attribute, or an entire set of bars can simply be made wider in a uniform way to be more visible
- points: intrinsically convey information only about position and are exactly the vehicle for conveying additional information through area and shape (and color!)

:::

---

### 1.2.3 Channel types

Two kinds of sensory modalities:

1. **Identity**: what, where
2. **Magnitude**: how much

It does not make sense to ask magnitude questions for shape, color hue. We can ask about magnitudes with length, area or volume; color luminance or saturation; and angle/tilt/slope.

::: notes

>The human perceptual system has two fundamentally different kinds of sensory modalities. The **identity** channels tell us information about _what_ something is or _where_ it is. In contrast, the **magnitude** channels tell us _how much_ of something there is (Munzner 2014, p.99).

:::

---

### 1.2.4 Using marks and channels

<div style="height: 1em;"></div>

All channels are not equal.

The selection of marks and channels should be guided by the principles of **expressivenes** and **effectiveness**.

Once the most important attributes/variables for the desired insight have been identified, the selection of marks and channels should ensure that they are **encoded with the highest ranked**.

::: notes

>the same data attribute encoded with two different visual channels will result in different information content in our heads after it has passed through the perceptual and cognitive processing pathways of the human visual system (Munzner 2014, p.100)

- expresiveness: the visual encoding should express all of, and only, the information in the dataset attributes. Ordered data should be shown in a way that we perceive as ordered; unordered data SHOULD NOT be shown in a way that implies an ordering that does not exist.
- effectiveness: the importance of the channel (task abstraction, targets and actions) should match its salience, how noticeable it is. The most important attributes/variables should be encoded with the most effective channels, and less important attributes can be matched with less effective channels.

These can be combined to create a ranking of channels according to the type of data that is being visually encoded. 

:::

---

### 1.2.4 Using marks and channels

![Channels ranked by effectiveness according to data and channel type. Ordered data should be shown with the magnitude channels, and categorical data with the identity channels (Munzner 2014, p.102)](img/munzner-5.6.png){width=600}

::: notes

Channels related to spatial position are at the top of both lists, and they are the only ones appearing on both lists (none of the others are effective for both data types). This primacy applies only to 2D positions, 3D depth is a much lower-ranked channel

:::

---

### 1.2.4 Using marks and channels

<div style="height: 2em;"></div>

The choice of **which attributes/variables to encode with position** is the most central choice in visual encoding.

::: notes

the attributes encoded with position will dominate the user's mental model --their internal mental representation used for thinking and reasoning-- compared with those encoded with any other visual channel. 

:::

---

### 1.2.4 Using marks and channels

![Error rates accross visual channels (Munzner 2014, p.105)](img/munzner-5.8.png){width=600}

::: notes

Perceptual accuracy of each channel type: how accurate is the interpretation made by users depending on the type of channel used to represent certain data

:::

## 1.3 So, which graph?

![A. Abela (2006), [Choosing the right chart](http://extremepresentation.typepad.com/blog/2006/09/choosing_a_good.html). Interactive version: [Chart chooser](http://labs.juiceanalytics.com/chartchooser/index.html)](img/choosing-chart.png){width=600}

::: notes

Variable types and insights (Munzner's "targets") as *ingredients*, which *recipes* can be used to *cook* data visualization?

There are many tools for this, represented only one. 

<!--
[The Data Visualisation Catalogue](https://datavizcatalogue.com/search.html)
-->
:::

## Tableau: let's explore

<!-- ![Show me](img/tableau/tableau_mostrarme.gif){width=700} -->

<div style="height: 2em;"></div>

- Dimensions and measures (remember also blue _vs._ green)
- Encode = drag
- `Show me` tab

::: notes

Left column, `Data` tab: 

- dimensions contain qualitative values
- measures contain numeric, quantitative values (you can apply calculations to them and aggregate them)

Reminder (blue _vs._ green, [learn more](http://onlinehelp.tableau.com/current/pro/desktop/en-us/help.html#datafields_typesandroles.html?Highlight=dimensions%20measures)):

- green = continuous. Its values are treated as an infinite range. Generally, continuous fields add axes to the view.
- blue = discrete. Its values are treated as finite. Generally, discrete fields add headers to the view. 

Mapping variables to graphs is done, in Tableau, by dragging items from the left column to either: `Columns`/`Rows`, or `Marks`.

`Show me` tab displays the most common graphs and the minimum requirement of data for each graph. If graphs = recipes, lets us know which ingredients are required to cook a certain recipe.

Also works the other way round: if I select my ingredients from the left bar, the `Show me` tab highlights the recipes available for those ingredients.

(test some graphs)
- Source only > table
- add spent > table, pie chart etc

<!-- The # of marks in the status bar represents the number of items in the graph. Determined by the combination of dimensions:

- if no dimensions (only income), sum of everything (maximum aggregation)
- if 1 dimension (i.e. source), 1 mark for each unique value
- if +1 dimension (i.e. + quarter), cross table of no. of unique values in each dimension -->

Fields can be used more than once (redundant coding) for easier identification, by dragging to more than one place. barchart income (rows) + source (columns), source to colour

Options in `Show me` are different from the `Marks` box. Show me only allows graphs that _make sense_, very basic and tested graphs. Marks allows to _force_ graphs in case we need more complex displays. USE WITH CAUTION, possible to create graphs that make no sense or are misleading (change to "line" in Marks box)

:::

# 2. Promote insight

---

## Section outline

How can we enable easier insight through data visualization?

1. Change default settings
2. Make simpler graphs
3. Highlight observations
4. Add attributes as context
5. Add statistical information

Practice: build (not so) basic graphs

## 2.1 Change default settings {data-transition="none"}

<figure>

![Data source: [Berlin marathon times](https://github.com/hmelberg/berlin-marathon)](img/easieranalysis1.png)

<figcaption style="margin-top:0;"></figcaption>
</figure>

::: notes

Official results form the Berlin marathons. The default aggregation from the tool used to create this visualization presents an almost perfect normal distribution.

:::

## 2.1 Change default settings {data-transition="none"}

![Data source: [Berlin marathon times](https://github.com/hmelberg/berlin-marathon)](img/easieranalysis2.png)

::: notes

More detail (less aggregation) allows to see some highlighted bars

:::

## 2.1 Change default settings {data-transition="none"}

![Data source: [Berlin marathon times](https://github.com/hmelberg/berlin-marathon)](img/easieranalysis3.png)

::: notes

Even more detail (less aggregation) makes those bars stand out more and new ones appear: what is happening here?

:::

## 2.1 Change default settings {data-transition="none"}

![Data source: [Berlin marathon times](https://github.com/hmelberg/berlin-marathon)](img/easieranalysis4.png)

::: notes

vertical dashed lines show hour marks in red (3h, 4h, 5h, main goal times for marathon runners), half-hour marks in grey. People try to fit into their closest _rounded time_...

:::

## 2.2 Make simpler graphs

<div style="height:100px;">&nbsp;</div>

>Data-ink is the non-erasable core of the graphic, the non-redundant ink arranged in response to variation in the numbers represented. 

<figure style="text-align:right;">
  <figcaption>
Tufte 1983
</figcaption>
</figure>

::: notes

we should remove all non-data-ink and redundant data-ink, within reason, to increase the data-ink-ratio and create a sound graphical design. 

some redundancy is often more effective, however, most graphics don't struggle with understatement. In fact, most contain a stunning amount of excess ink (or pixels). Rather than dressing our data up we should be stripping it down.

:::

## 2.2 Make simpler graphs

<div style="margin:auto; width: 520px; height: 450px; position: relative;">
  <iframe src="https://speakerdeck.com/player/87bb9f00ec1e01308020727faa1f9e72" style="border: 0; top: 0; left: 0; width: 520px; height: 450px; position: absolute;" allowfullscreen scrolling="no"></iframe>
</div>

<figure>
  <figcaption>
  A step-by-step example: [Data looks better naked](http://www.darkhorseanalytics.com/blog/data-looks-better-naked)
</figcaption>
</figure>

::: notes

In it we start with a chart, similar to what we've seen in many presentations, and vastly improve it with progressive deletions and no additions.

The next time you are trying to improve a chart, consider what you can take away rather than what you can add.

:::

## 2.2 Make simpler graphs 

More on decluttering:

<figure>
<iframe width="560" height="315" src="https://www.youtube.com/embed/X79o46W5plI" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

<figcaption style="margin-top:0;">Nussbaumer, [Declutter Your Data Visualizations](https://www.youtube.com/embed/X79o46W5plI)</figcaption>
</figure>

## 2.3 Highlight observations

Through [preattentive attributes](https://www.interaction-design.org/literature/article/preattentive-visual-properties-and-how-to-use-them-in-information-visualization):

- they are processed in spatial memory without our conscious action
- make it easier to understand what is represented through a design: saves from consciously processing data

::: notes

A preattentive visual property is one which is processed in spatial memory without our conscious action. In essence it takes less than 500 milliseconds for the eye and the brain to process a preattentive property of any image.  These properties can be harnessed to make it easier for a user to understand what is presented through the design and save them from consciously processing all the data presented in short-term memory which requires more effort.

:::

## 2.3 Highlight observations

![Nussbaumer 2015, p.103](img/nussbaumer-4.2.png)

::: notes

There are 6. No visual cues to help count. It makes this a challenging exercise, you have to hunt through the lines of text, looking for the number 3.

What happens when we make a single change to the block of numbers. Repeat the exercise of counting the number 3s.

:::

## 2.3 Highlight observations

![Nussbaumer 2015, p.104](img/nussbaumer-4.3.png)

::: notes

Note how much easier and faster the same exercise is. There is no time to blink, no time to think, no NEED to think. The preattentive attribute of intensity of color in this case, makes the number 3s stand out from the rest. Our brain is quick to pick them up without having to dedicate any conscious thought to it.

:::

## 2.3 Highlight observations

![Nussbaumber 2015, p.105](img/nussbaumer-4.4.png){width=650}

::: notes

your eye is drawn to the one element within each group that is different from the rest, you don't have to look for it. Our brain is hardwired to quickly pick up differences we see in the environment.

NOTE that people tend to associate quantitative values to some of the preattentive attributes (length, width, size; not colour). This tells us which of the attributes can be used to code quantitative information  (line
length, spatial position, or to a more limited extent, line width, size,
and intensity can be used to reflect relative value), and which should
be used as categorical differentiators.


:::

## 2.3 Highlight observations 

![Nussbaumber, [Do you see it? The importance of contrast when communicating with data [video]](https://www.youtube.com/watch?v=60KiAXbkrl0)](img/nussbaumer-contrast.png){width="700px"}

::: notes

After decluttering, more _channels_ are available for highlight. This allows to

1. draw your audience’s attention quickly to where you want them to look, and 
2. create a visual hierarchy of information

:::

## 2.4 Add variables (as context)

- Adding preexisting variables (in moderation)
- Creating conditional variables from preexisting variables
    - binaries or with few levels are best
    - <span style="font-size:.9em;">example of calculated field or variable: weekend date</span>

![](img/addvariables.png){.fragment}

::: notes

useful only if addition conveys meaning / enables insight. In the graph, the colour coding is explanatory to the left, but it is not to the right. 

:::

## 2.5 Add statistical information

<figure style="float:right;width:50%;" class="fragment">
<img src="img/addstatinfo1.png" />

<figcaption>
[source](https://stackoverflow.com/questions/13254441/add-a-horizontal-line-to-plot-and-legend-in-ggplot2)
</figcaption>
</figure>

<div style="height:2em;"></div>

- statistical summaries <br /> (mean, variance)
- models

## Tableau: (not so) basic graphs

<div style="height:3em;"></div>

![Sparklines ([Tufte 2006](https://www.edwardtufte.com/bboard/q-and-a-fetch-msg?msg_id=0001OR))](img/sparkline_d3_angular.png){width=400}

::: notes

Select Quarter and Income, line graph from Show me.

Quarter: will default to higher level of aggregation (YEAR). Possible to select different aggregations (when and if attribute is correctly interpreted): year > q > month...

When selecting aggregate levels with dates (by clicking on arrow):

- top half considers date as discrete (will change to blue if selected). Useful to compare the same period of time in different years.
- bottom half considers date as continuous.

Source to rows will draw one graph per source. 

Rename sheet to `Sparkline`, Save.

:::

## Tableau: (not so) basic graphs

<div style="height:2em;"></div>

![Bulletgraphs ([Few 2007](https://www.perceptualedge.com/articles/misc/Bullet_Graph_Design_Spec.pdf))](img/bulletgraph-plain.png)

## Tableau: (not so) basic graphs {data-transition="none"}

<div style="height:2em;"></div>

![[Bulletgraphs (Few 2007)](https://www.perceptualedge.com/articles/misc/Bullet_Graph_Design_Spec.pdf)](img/bulletgraph-annotated.png)

::: notes

Source to rows, income to columns > draws bars.

Where is goal? Drag to columns > two different graphs (not what we want).

Select source + income + goal > bullet graph from Show me.

Shows totals, may not be what we want. Anyway, what did this do? Now manually:

1. source to rows, income to columns
2. now we want goal as black bar (reference line), goal valorations as background (distribution band)
3. Double click on ref. line, adds a line of average income
  - scope: default `per pane`: avg per each _combination_. `per table`, whole table (same as per pane when there is only one dimension). `per cell` avg. per each mark.
  - line: only shows income for now. How to add goal? Drag to Marks > detail, not going to display but is available to use. Now line: sum(goal), label (none).
  - formatting: bolder, black
4. Double click on distribution band.
  - scope: per cell
  - computation: value: 60%/80%, percent of sum(goal) instead of income. label: none
  - formatting: check fill below (used normally in bullet graphs because _below_ is usually bad)
  
Style:

- Marks > size, make thinner bars to make background more visible
- Format > lines:
  + rows: grid lines, solid white 
  + columns: none

Rename sheet to bullet graph, save.

:::

## Tableau: (not so) basic graphs

![[Heatmaps (Few 2006)](https://www.perceptualedge.com/articles/b-eye/heatmaps.pdf)](img/heatmap1.png){width=600}

::: notes

Source + quarter + income > Show me, heatmap. Columns YEAR, click on + (adds column Q)

In Marks, sum(income) is redundant as label and color. If remove label, pure heatmap

Interpretation: 

- both years sho low levels for FB on Q3, why?
- both years are _hotter_ on Q2, why?

:::

<!--
Timelines

![Timelines](img/tableau_timeline_1080x768.gif){width=700}

Bulletgraphs

![Bulletgraphs](img/tablea_bulletgraph_1080x768.gif){width=700}

Heatmaps

![Heatmaps](img/tablea_heatmap_1080x768.gif){width=700}

Automatic aggregation

![Automatic aggregation](img/tablea_campos_calculados_1_agregaciones_de_tableau1080x768.gif){width=700}

Calculated fields

![Calculated fields](img/tablea_campos_calculados_2_campo_calculado_nivel_linea1080x768.gif){width=700}

Aggregation on calculated fields

![Aggregation on calculated fields](img/tablea_campos_calculados_3_agregaciones_sobre_campos_calculados1080x768.gif){width=700}

Adding KPIs to timelines 1

![Adding KPIs to timelines 1](img/tablea_sparkline_kpi_1_anadir_kpi_basico1080x768.gif){width=700}

Adding KPIs to timelines 2

![Adding KPIs to timelines 2](img/tablea_sparkline_kpi_2_anadir_mas_kpi1080x768.gif){width=700}

-->

# 3. Dashboards

---

## Section outline

1. What is a dashboard?
2. Common design mistakes
3. Key goals in the visual design process
4. Example

Practice: layout and format graphs into a dashboard

## 3.1 What is a dashboard?

<blockquote style="margin-top:2em;">
  <p style="margin:0 !important;">
Visual display of the most information needed to achieve one or more objectives
which fits entirely on a single computer screen so it can be monitored at a glance.
</p>
</blockquote>

<figure style="text-align:right !important;">
  <figcaption>Few 2013</figcaption>
</figure>

::: notes

When they work, they provide a powerful means to tame the beast of data overload. Most dashboard live however to a fraction of their potential, not because of poor technology, but because of poor design.

They must grab your attention when it's needed, make it easy to spot what's most important in a screen full of data, and give you the means to understand what's happening (_insight_) and respond without delay.

Not designed to wow people upon first sight, but to inform people with precisely what they need in the way they need it day in and day out. 

:::

## 3.1 What is a dashboard?

>- **Visual display**: _I see_  =  _I understand_  &rarr;  _insight_
 **to achieve specific objectives**: may require gathering information that is otherwise unrelated or disperse
>- **fits in a single computer screen**: it must all be seen at once (short-term memory effect)
>- **monitored at a glance**: doesn't need to provide all the details, but if it doesn't, it should make it as easy and seamless as possible to get to that information


::: notes

- combine text and graphs, with emphasis on graphics. There is such an intimate connection between what we see and how we think, we actually use the expression "I see" as a substitute for "I understand". when we make sense of something, we refer to what we've learned as "insight". the more you can rely on images to tell the story, the faster it can be perceived. We perceive images in a parallel manner, which is **much faster than the serial/sequential perception of language**.  We have very limited short-term memory: dashboards address this issue in two ways:
  + making the content in each slot more "information rich"  (only 4-5 slots; numbers/graphs?)
  + reducing the need to rely on it, everything relevant is available simultaneously. External form of memory.

Must the information be constantly refreshed in real time? Only if the objectives that it serves require real‐time information. If you are monitoring air traffic using a dashboard, you must immediately be informed when something is wrong. On the other hand, if you are making strategic decisions about how to boost sales, a snapshot of information as of last night, or perhaps even the end of last month, should work fine.

:::

## 3.2 Common design mistakes

>- Exceeding the boundaries of a single screen
>- Supplying inadequate context for the data
>- Displaying excessive detail or precision
>- Choosing a deficient measure
>- Choosing inappropriate display media
>- Introducing meaningless variety
>- Using poorly designed display media

<div style="text-align:right;font-size:.7em;">_continues..._</div>

::: notes

- more than one srceen (or scrolling) requires to rely on short-term memory, far more processing effort from the mind.
- values compared to what? good or bad? how good or bad? are we on track?
- too much detail slow users down without any benefit, makes her filter out what is important
- spent & income instead of benefit, two values instead of ratios for example
- choosing the right graph (previous section)
- 
- channels without attribute/reference variable, specially colour

:::

## 3.2 Common design mistakes

<div style="font-size:.7em;">_...continued_</div>

>- Encoding quantitative data inaccurately
>- Arranging the data poorly
>- Highlighting important data ineffectively or not at all 
>- Cluttering the display with useless decoration 
>- Misusing or overusing color 
>- Designing an unattractive visual display 

::: notes

- non-zero (vertical) axis for example
- top-left is most prominent, bottom-right the less prominent area. use accordingly
- should draw eyes to most relevant information regardless of location. too much highlight means no highlight at all = if everything is prominent, nothing is prominent
- blank space is always bettern than meaningless decoration. If logos must be used, make them small and visually subtle, and place them out of the way
- REMEMBER colour is a channel that should almost always refer to an attribute/variable
- not excessively decorated does not mean unattractive. no need to add touches to make the dashboard pretty, but rather attractively display the data itself

:::

## 3.3 Key goals in the visual design process

<div style="height:2em;"></div>
From previous section:

- make simpler graphs (declutter)
- highlight observations
- add attributes/variables as context or statistical information

## 3.3 Key goals in the visual design process

In other words:

1. Reduce non-data pixels
  - eliminate all unnecessary non-data pixels
  - de-emphasize and regularize the non-data pixels that remain
2. Enhance data pixels
  - eliminate all unnecessary data pixels
  - highlight the most important data-pixels that remain

::: notes

1. reduce
  - decoration graphics, variations in color without meaning, borders or background colours as separation instead of whitespace, gradients instead of solid colour, grid lines (graphs or tables), fill colours for alternating rows, unjustified additional dimensions (specially 3D)...  (channels without attribute)
  - ocassionally useful non-data pixels to de-emphasize: axis lines,  borders or backgrounds as separation, grid lines, legends
2. enhance
  - show only what is really needed: eliminate unnecessary data, condensate and summarize, level of detail should not exceed what's necessary
  - depends on desired type of insight. Some are always important (static means of emphasis), some are only important when certain conditions are met (alerts, require dynamic means of emphasis)

:::
<!--
## 3.1 Dashboards for *situation awareness*

<div style="height:1em;"></div>

> The term “dashboard” refers to a single screen information display that is used to monitor what’s going on in some aspect of the business. 

<figure style="text-align:right;">
<figcaption>Few (2007), [Dashboard Design](https://www.perceptualedge.com/articles/Whitepapers/Dashboard_Design.pdf)
</figcaption></figure>

## 3.1 Dashboards for *situation awareness*

<div style="height:1em;"></div>

- Perception of own's environment
- Comprehension of it's meaning
- Projection of that understanding into the future

## 3.2 Dos: Principles to follow

- Use flicker and sound to grab attention
- Encourage active thinking about the data, not just passive reaction to alarms
- Don’t over-automate actions to the point where people become disengaged
- Provide smooth and simple means to respond
- Provide a common picture for the whole team
- Support projections for proactive responses
- Match the mental model

## 3.3 ...and Don'ts: Design problems to avoid

- Too much complexity
- Too many alert conditions
- Alerts that cannot be diff erentiated
- Overwhelming visuals
- Distracting visuals
- Inappropriate visual salience
- Mismatch between information and its visual representation
- Indirect expression of measures
- Not enough context
-->

## 3.4 Example

![Few 2013](img/sfew_capture.gif){width=650}

::: notes

- colour is used sparingly. headings separate sections, the only other colour different from gray is on red alerts. colours do not compete with each other for attention
- the prime real estate on the screen has been used for the most important data: upper-left corner of the screen
- small, concise display media have been used to support the display of a dense set of data in a small amount of space. sparklines and bullent graphs convey a lot of information without looking cluttered
- legends are unobtrusive
- white space alone has been used to delineate and group data (no borders, grid lines, background fills)
- not cluttered with instructions and descriptions that are only occasionally needed (those in "Help")
- 

:::

## Dashboards in Tableau

<!--
![Basic dashboard](img/tableau/tablea_dashboard_1_montar_dashboard1080x768.gif){width=700}
-->

<div style="height:2em;"></div>

Dashboards in Tableau are containers of _sheets_ of graphs.

Allow for quite basic but functional formatting.

<!--
  ![Basic formating](img/tableau/tablea_dashboard_2_formateo_basico1080x768.gif){width=700}
-->

::: notes

New dashboard. Dashboards in Tableau are container of _sheets_ of graphs. Dashboard size is selected depending on destination format (screen or paper, size...). Choose small, 640x420

- Sheets area shows graphs we have created.
- Objects displays additional layout elements that could be used

Drag elements to window: Sparklines top-left, bullet graphs top-right, heatmap bottom

Hide headers 

:::

<!--
## Tableau 2.3: show filters

![Show filters](img/tableau/tablea_dashboard_3_mostrar_filtro1080x768.gif){width=700}
-->

## Tableau: Actions

<div style="height:2em;"></div>

Some degree of interactivity with `Actions`: highlight and filter

<!--
![Highlight action](img/tableau/tablea_dashboard_4_accion_highlight1080x768.gif){width=700}

![Filter action](img/tableau/tablea_dashboard_5_accion_filtro1080x768.gif){width=700}
-->

::: notes

We can add a minimum level of interactivity

Dashboard > Actions, Highlight.

- source: sparkline
- target: all

Dashboard > Actions, Filter.

- source: sparkline, run on select
- target: all

:::

## Tableau: What else?

<div style="height:2em;"></div>

Calculated fields

...

::: notes

spent/income ratio, spent/visits ratio, income/visits ratio...

:::

# Epilogue

## What? I want more!

- Tableau, [Free Training Videos](https://www.tableau.com/learn/training)
  - Tableau, [Análisis visual: como aprovechar las características cognitivas humanas para comprender tus datos](https://www.tableau.com/es-es/learn/webinars/visual-analytics)
- Coursera, [Visual Analytics with Tableau](https://es.coursera.org/learn/dataviz-visual-analytics)
- Udemy, [(Ranked) Data Visualization Courses](https://www.udemy.com/topic/data-visualization/)


---

<h1>References</h1> 

<div style="font-size:.5em;width:90%;margin:1em auto;">
  Abela, Andrew (2006). [Choosing a good chart](http://extremepresentation.typepad.com/blog/2006/09/choosing_a_good.html).

  Few, Stephen (2009). [Dashboard Design for Real-Time Situation Awareness](https://www.perceptualedge.com/articles/Whitepapers/Dashboard_Design.pdf) [White Paper]

  &mdash; (2013). _Information Dashboard Design_. Analytics Press: [`316.763 F 44 s`](https://oceano.biblioteca.deusto.es/primo-explore/fulldisplay?docid=DEUSTO_Alma21135421430003351&context=L&vid=deusto&search_scope=default_scope&tab=default_tab&lang=es_ES)

  Kirk, Andy (2016). _Data Visualisation: A Handbook for Data Driven Design_. SAGE: London [`316.763 K 63 a`](https://oceano.biblioteca.deusto.es/primo-explore/fulldisplay?docid=DEUSTO_Alma21137802850003351&context=L&vid=deusto&lang=es_ES&search_scope=default_scope&adaptor=Local%20Search%20Engine&tab=default_tab&query=any,contains,andy%20kirk&sortby=rank&offset=0)

  Munzner, Tamara (2015). _Visualization Analysis and Design_. CRC Press: Boca Raton, Florida [`316.763 M 92 t`](https://oceano.biblioteca.deusto.es/primo-explore/fulldisplay?docid=DEUSTO_Alma21159285450003351&context=L&vid=deusto&search_scope=default_scope&tab=default_tab&lang=es_ES)

  Tufte, Edward R. (1983). _The Visual Display of Quantitative Information_. Graphics Press: California [`316.763 T 87 e`](https://oceano.biblioteca.deusto.es/primo-explore/fulldisplay?docid=DEUSTO_Alma21132751690003351&context=L&vid=deusto&search_scope=default_scope&isFrbr=true&tab=default_tab&lang=es_ES)
</div>

---

<div style="text-align:center;">

<h1>Thank you!</h1>

This presentation is available at <br />[`http://mrn.bz/MUMA2018`](http://mrn.bz/MUMA2018)

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