## List of Charts


### - [AreaChart](./charts/area-chart.js)

A basic Area Chart For displaying multiple sets of data grouped to one x axis.

#### Features:

By scrolling the pointer over a xkey data point, A tooltip will appear with xkey data point name and corresponding ykey data point names and values.

#### Usage:

Props: This component takes 6 values.

```javascript

id = 'chart' (A string signifying the unique id of the chart)
data = '{[{ xkey_string: 'Any String', ykey_string: Any_Number }]}' (Where xkey_string is a variable with the same verbatim name as string defined in xkey prop)
                                                                     (Where ykey_string is a variable with the same verbatim name as one of the strings defined in ykeys prop)
xkey = 'Any Unique String' 
ykeys =  ['Any Unique String', 'Any Unique String']
labels = ['A String', 'A String'], (Directly Correlational to ykeys index)
lineColors = ['A Hex Color', 'A Hex Color'], (Directly Correlational to ykeys index)

```

#### Default Values:

These Prop values are used if none are supplied.

    id : 'area-chart-1',
    data : [
        {y: '2011 Q1', item1: 2666, item2: 2666},
        {y: '2011 Q2', item1: 2778, item2: 2294}
    ],
    xkey : 'y',
    ykeys: ['item1', 'item2'],
    labels: ['Item 1', 'Item 2'],
    lineColors: ['#a0d0e0', '#3c8dbc']

#### Example: 

```javascript
<AreaChart 
    id="revenue-chart"
    data = {[
        {y: '2011 Q1', item1: 2666, item2: 2666},
        {y: '2011 Q2', item1: 2778, item2: 2294},
        {y: '2011 Q3', item1: 4912, item2: 1969},
        {y: '2011 Q4', item1: 3767, item2: 3597},
        {y: '2012 Q1', item1: 6810, item2: 1914},
        {y: '2012 Q2', item1: 5670, item2: 4293},
        {y: '2012 Q3', item1: 4820, item2: 3795},
        {y: '2012 Q4', item1: 15073, item2: 5967},
        {y: '2013 Q1', item1: 10687, item2: 4460},
        {y: '2013 Q2', item1: 8432, item2: 5713}
    ]}
    xkey= 'y'
    ykeys= {['item1', 'item2']}
    labels= {['Item 1', 'Item 2']}
    lineColors= {['#a0d0e0', '#3c8dbc']} />
```
![](../../../../../screenshots/area-chart.png)



### - [DonutChart](./charts/donut-chart.js)

A basic Donut Chart for displaying data as percentages of all data.

#### Features:

By scrolling the pointer over a slice of the donu chart, the selected slice will enlargen and create a secondary line to indicate selection. 
    The label and value of the selected slice will also be displayed in the center of the chart.

#### Usage:

Props: This component takes 3 values.

```javascript

id = 'chart' (A string signifying the unique id of the chart)
data = {[{label: 'Any String', value: 'Any_Number'},{label: 'Any String', value: 'Any_Number'}]} (Each Element is a Slice of the circle represented by an object with a label and value)
colors = {['A Hex Color', 'A Hex Color']} (Directly Correlational to data object index)

```
#### Default Values:

These Prop values are used if none are supplied.

    id: 'donut-chart-1',
    colors: ['#3c8dbc'],
    data: [
        {
            label: "Donut piece", value: 40
        }
    ]

#### Example: 

```javascript
<DonutChart 
    id="sales-chart"
    colors= {["#3c8dbc", "#f56954", "#00a65a"]}
    data= {[
        {label: "Download Sales", value: 12},
        {label: "In-Store Sales", value: 30},
        {label: "Mail-Order Sales", value: 20}
    ]} />
```
![](../../../../../screenshots/donut-chart.png)

### - [WorldMap](./charts/world-map.js)

A World Map That gives different gradients based upon input values.

#### Features:

Displays a map of the world with a (+) button for zooming inwards and a (-) button for zooming outwards.

#### Usage:

Props: This component takes 2 values.

```javascript

id = 'world-map' (A string signifying the unique id of the chart)
info = {{"ISO ALPHA-2 Code": "Any Number"}} (The Shade of the number is directly correlational to the magnitude of the number)


```
#### Supplementary Info:

What is ISO ALPHA-2? 

    ISO ALPHA-2 is a international convention providing a two character code to countries and regions around the world.
    For a Full List Wikipedia to the rescue: https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2


#### Example: 

```javascript
<WorldMap 
    id="world-map"
    info = {{
        "US": 398,
        "SA": 400, 
        "CA": 1000, 
        "DE": 500, 
        "FR": 760, 
        "CN": 300, 
        "AU": 700, 
        "BR": 600, 
        "IN": 800,
        "GB": 320, 
        "RU": 3000 
    }} />
```
![](../../../../../screenshots/world-map.png)


## List of Containers

##### Why a Container?

    The Container Class is meant to organize and group common components so that they can be constructed and displayed without actually changing the component code itself. 
    It helps maintain a uniform look and feel throughout the UI.

### - [ContainerOne](./containers/container-one.js)

A Container to Display Two Charts

#### Features:

Generates Two Tabs linked to a #revenue-chart and #sales-chart IDs and loads the content of said properly ID'd children. 

#### Usage:

Props: This component takes 0 values but requires two children divs (which it loads as props) with IDs mentioned above.

    Why a Container?

    This Container in particular groups two common chart types used primarily for data analysis.
        

#### Example: 

```javascript
<ContainerOne>
    <AreaChart 
        id="revenue-chart"
        data = {[
            {y: '2011 Q1', item1: 2666, item2: 2666},
            {y: '2011 Q2', item1: 2778, item2: 2294},
            {y: '2011 Q3', item1: 4912, item2: 1969},
            {y: '2011 Q4', item1: 3767, item2: 3597},
            {y: '2012 Q1', item1: 6810, item2: 1914},
            {y: '2012 Q2', item1: 5670, item2: 4293},
            {y: '2012 Q3', item1: 4820, item2: 3795},
            {y: '2012 Q4', item1: 15073, item2: 5967},
            {y: '2013 Q1', item1: 10687, item2: 4460},
            {y: '2013 Q2', item1: 8432, item2: 5713}
        ]}
        xkey= 'y'
        ykeys= {['item1', 'item2']}
        labels= {['Item 1', 'Item 2']}
        lineColors= {['#a0d0e0', '#3c8dbc']} />
        
    <DonutChart 
        id="sales-chart"
        colors= {["#3c8dbc", "#f56954", "#00a65a"]}
        data= {[
            {label: "Download Sales", value: 12},
            {label: "In-Store Sales", value: 30},
            {label: "Mail-Order Sales", value: 20}
        ]} />
</ContainerOne>

```

More To Come!

