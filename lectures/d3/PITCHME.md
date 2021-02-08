---?color=black
@title[Title]

@snap[west headline text-white span-70]
d3

@snapend

@snap[south-west]
@fa[envelope-o pad-right-icon]@css[contact-email](thomas.devine@lyit.ie)
@snapend

---
@title[Contents]
### Contents

@ol[](false)
- **What is D3?**
- SVG
- d3 Setup
- d3 Bar Chart
- d3 Data Binding
@olend

---
@title[What is D3?]
### What is D3?

@ul[](true)
- [See](https://vimeo.com/29862153) what can D3 do
- D3 makes graphics within a web page from data
- D3 does data visualisations
@ulend


---
@title[What is D3?]
### What is D3?

@ul[](true)
- D3 is an abbreviation of Data-Driven Documents
- It's another JavaScript library file
- Get latest version @ [d3.org](https://d3js.org/)
- Link to D3 using `<script>` element like this:
@ulend

```html
<script src="https://d3js.org/d3.v4.min.js"></script>
```


---
@title[What is D3?]
### What is D3?

@ul[](true)
- There are no predefined charts in D3
- Just shapes, lines and text
- For example, to create a bar chart you must create the bars, axes, and text yourself
@ulend

![](images/barChart.png)


---
@title[What is D3?]
### What is D3?

@ul[](true)

- This allows you to devise/create new types of custom charts
- But you build from the ground up
- D3 uses **SVG** to do the drawing
@ulend

![](images/barChart.png)

---
@title[Contents]
### Contents

@ol[](false)
- What is D3?
- **SVG**
- d3 Setup
- d3 Bar Chart
- d3 Data Binding
@olend


---
@title[SVG]
### SVG

@ul[](true)
- SVG is Scalable Vector Graphics
- There are two kinds of digital graphic - raster and vector
- Raster images like photographs use many colored pixels to form an image, e.g. JPEGs, GIFs and PNGs
- They can't be resized much without loss of resolution
- A vector graphic appears like any image, but it is a mathematical definition
- Vector images never loses definition
- SVG is ideal for data visualisations
@ulend



---
@title[SVG]
### SVG

@ul[](true)
- HTML has a `<svg>` element
- It can be placed anywhere inside the `<body>` element
- D3 uses the `<svg>` tag as a container to put charts into
- The `<svg>` tag can only contain specific graphical elements like lines, rectangles, etc.
- D3 adds graphical elements to the SVG and **binds data** to them
- For example, D3 could read 50 data values from an array and add 50 circles to the SVG
- An [SVG Tutorial](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial)
@ulend


---
@title[SVG Example]
<!-- ### SVG Example -->

```html
<html>
<body>
<svg width="300" height="200">
  <rect x="0" y="0" width="300" height="200" fill="red" />
  <circle cx="150" cy="100" r="80" fill="green" />
  <text x="150" y="125" font-size="60" text-anchor="middle">SVG</text>
</svg>
</body>
</html>
```
@[3,7](svg container)
@[3-7](content)
@[*]()

![](images/svgExample1.png)

[@fa[external-link]](http://localhost/d3/svgExample.html)


---
@title[SVG]
### SVG 

SVG has some basis shapes like:

@ul[list-fade-fragments]
- Rectangles
- Circle
- Ellipse
- Line
- Polyline
- Polygon
- Path (alternative to Polyline and Polygon)
@ulend

@ul[](true)
* See and learn them [here](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Basic_Shapes)
* Let's see a simple bar chart...
@ulend


---

![](images/barChart1.png)

[@fa[external-link]](http://localhost/d3/svgBarChart.html)

And the code...


---
@title[SVG Bar Chart]
<!-- ### SVG Bar Chart -->

```html
<html>
<body>
<svg width="300" height="200">
  <rect x="0" y="0" width="100" height="50" 
        fill="steelblue" />
  <rect x="0" y="60" width="200" height="50" fill="steelblue" />
  <rect x="0" y="120" width="300" height="50" fill="steelblue" />

  <text x="10" y="35" font-size="20" fill="white">100</text>
  <text x="10" y="95" font-size="20" fill="white">200</text>
  <text x="10" y="155" font-size="20" fill="white">300</text>
</svg>
</body>
</html>
```
@[3,12](svg container)
@[3,4-7,12](rectangles)
@[3,9-11,12](text)
@[*]()

[@fa[external-link]](http://localhost/d3/svgBarChart.html)


---
@title[SVG]
### SVG Bar Chart 2.0

@ul[list-fade-fragments]
- Previously, the values in our bar chart were static
- JavaScript could draw it dynamically like this..
@ulend

---
@title[SVG Bar Chart]

<pre>- svgBarChart2.html -</pre>

```html
<html>
<head>
<script type="text/javascript" src="svgBarChart2.js"></script>
</head>
<body>

<svg id="chart"></svg>

</body>
</html>
```

---
@title[SVG Bar Chart]

<pre>- svgBarChart2.js -</pre>

```javascript
var data = [100,200,300]; // can add new values

$(document).ready(function() {
  document.getElementById('chart').setAttribute('width',300);
  document.getElementById('chart').setAttribute('height',data.length*60);

  for(var i=0;i<data.length;i++) {
    var rect=document.createElementNS("http://www.w3.org/2000/svg","rect");
    rect.setAttribute('x',0);
    rect.setAttribute('y',i*60);
    rect.setAttribute('width',data[i]);
    rect.setAttribute('height',50);
    rect.setAttribute('fill','steelblue');
    document.getElementById('chart').appendChild(rect);
  }
}
```

See code [here](http://localhost/d3/svgBarChart2.html)


---
@title[d3 Data Binding]
### D3 Exercise 1 – SVG

[@fa[external-link]](https://github.com/noucampdotorgSSAD2021/d3/blob/main/exercises/D3Ex1.md)



---
@title[Contents]
### Contents

@ol[](false)
- What is D3?
- SVG
- **d3 Setup**
- d3 Bar Chart
- d3 Data Binding
@olend


---
@title[d3 Setup]
### d3 Setup

@ul[](true)
- Download d3 from [https://d3js.org/](https://d3js.org/)
- OR use `d3` directly from [https://d3js.org/](https://d3js.org/)
- Use it with a `<script>` tag like this...
@ulend

---

```javascript
<!doctype html>
<html>
<head>
  <script type="text/javascript" src="d3.min.js"></script>
</head>
...
...
```
OR
```javascript
<!doctype html>
<html>
<head>
  <script src="https://d3js.org/d3.v6.min.js"></script>
</head>
...
...
```



---
@title[Contents]
### Contents

@ol[](false)
- What is D3?
- SVG
- d3 Setup
- **d3 Bar Chart**
- d3 Data Binding
@olend


---
Previously we used these tags – `<svg>`, `<rect>` and `<text>` to draw a chart
```html
<html>
<body>

<svg width="300" height="200">
<rect x="0" y="0" width="100" height="50" fill="steelblue" />
<rect x="0" y="60" width="200" height="50" fill="steelblue" />
<rect x="0" y="120" width="300" height="50" fill="steelblue" />

<text x="10" y="35" font-size="20" fill="white">100</text>
<text x="10" y="95" font-size="20" fill="white">200</text>
<text x="10" y="155" font-size="20" fill="white">300</text>
</svg>

</body>
</html>

```

[@fa[external-link]](http://localhost/d3/svgBarChart.html)

---

Let's use D3 this time...

---
`- d3BarChartJQ.html -`

```html
<!doctype html>
<html>
<head>
    <script src="https://code.jquery.com/jquery-3.5.1.min.js" integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" crossorigin="anonymous"></script>
    <script src="https://d3js.org/d3.v6.min.js"></script>
    <script type="text/javascript" src="d3BarChartJQ.js"></script>  
</head>

<body>
</body>

</html>

```

[@fa[external-link]](http://localhost/d3/d3BarChartJQ.html)

---
`- d3BarChartJQ.js 1/3 -`

```javascript
$(document).ready(function() {

  var svg = d3.select("body").append("svg")
                              .attr("width",300)
                              .attr("height",200);
  ...
});
```

[@fa[external-link]](http://localhost/d3/d3BarChartJQ.html)


---
`- d3BarChartJQ.js 2/3 -`

```javascript
$(document).ready(function() {

  var svg = d3.select("body").append("svg")
                              .attr("width",300)
                              .attr("height",200);
  svg.append("rect")
      .attr("x",0)
      .attr("y",0)
      .attr("width",100)
      .attr("height",50)
      .attr("fill","steelblue");
  ...
});

```

[@fa[external-link]](http://localhost/d3/d3BarChartJQ.html)

---
`- d3BarChartJQ.js 3/3 -`

```javascript
$(document).ready(function() {

  var svg = d3.select("body").append("svg")
                              .attr("width",300)
                              .attr("height",200);
  ...
  svg.append("rect")
      .attr("x",0).attr("y",60)
      .attr("width",200).attr("height",50).attr("fill","steelblue");
  svg.append("rect")
      .attr("x",0).attr("y",120)
      .attr("width",300).attr("height",50).attr("fill","steelblue");
});

```

[@fa[external-link]](http://localhost/d3/d3BarChartJQ.html)


---
@title[d3 Data Binding]
### D3 Exercise 2 – D3 Fundamentals - Part 1

[@fa[external-link]](https://github.com/noucampdotorgSSAD2021/d3/blob/master/exercises/D3Ex2.md)



---
@title[Contents]
### Contents

@ol[](false)
- What is D3?
- SVG
- d3 Setup
- d3 Bar Chart
- **d3 Data Binding**
@olend


---

`- d3BarChartJQ.html -`

```html
<!doctype html>
<html>
<head>
    <script src="https://code.jquery.com/jquery-3.5.1.min.js" integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" crossorigin="anonymous"></script>
    <script src="https://d3js.org/d3.v6.min.js"></script>
    <script type="text/javascript" src="d3BarChartJQ.js"></script>  
</head>
<body>
</body>
</html>
```

---

```javascript
$(document).ready(function() {
    var svg = d3.select("body").append("svg").attr("width",300).attr("height",200);
    svg.append("rect")
        .attr("x",0).attr("y",0)
        .attr("width",100)
        .attr("height",50).attr("fill","steelblue");
    svg.append("rect")
        .attr("x",0).attr("y",60)
        .attr("width",200)
        .attr("height",50).attr("fill","steelblue");
    svg.append("rect")
        .attr("x",0).attr("y",120)
        .attr("width",300)
        .attr("height",50).attr("fill","steelblue");    
});
```
@[5,9,13](Previously bar values were static)

---
@title[d3 Data Binding]
### d3 Data Binding

@ul[](false)
- Let's get the data from an array instead
@ulend

```javascript
$(document).ready(function() {
    var dataset = [100, 200, 300];
    var svg = d3.select("body").append("svg")
                                .attr("width",300)
                                .attr("height",200);
    ...
    ...
});
```
@[2](dataset with values)
@[*]()


---
@title[d3 Data Binding]
### d3 Data Binding

@ul[](false)
- Let's bind array data to `rect` elements using `data()`
@ulend

```javascript
$(document).ready(function() {
  var dataset = [100, 200, 300];
  var svg = d3.select("body").append("svg")
                              .attr("width",300)
							  .attr("height",200);
  var elements = svg.selectAll("rect")
					 .data(dataset);
  console.log(elements);
});
```
@[6,7]()
@[*]()

[@fa[external-link]](http://localhost/d3/d3BarChartJQ2.html)

@ul[](true)
- Wait - there are no `rect` elements in the `svg`!!
- But, the array values are added to a d3 ``enter`` selection
@ulend

---
@title[d3 Data Binding]
### d3 **enter** selection

@ul[](true)
- The enter selection is a placeholder (array) for data items that have no corresponding DOM element
- The enter selection is typically used to create missing elements corresponding to new data
- We'll use the ``enter()`` function to get the data items and ...
- bind them to SVG ``rect`` items.
@ulend

---
@title[d3 Data Binding]
### d3 Data Binding

```javascript
$(document).ready(function() {
  var dataset = [100, 200, 300];
  var svg = d3.select("body").append("svg")
                              .attr("width",300)
							  .attr("height",200);
  var elements = svg.selectAll("rect")
					 .data(dataset);
  elements.enter().append("rect");
});
```
@[8](each data value in enter selection is associated with a rect)
@[*]()

[@fa[external-link]](http://localhost/d3/d3BarChartJQ3.html)

@ul[](true)
- The number of data items determines the number of elements
- a data driven document!!
@ulend

---
@title[d3 Data Binding]
### d3 Data Binding

Let's add the ``rect`` attributes...

---
@title[d3 Data Binding]
### d3 Data Binding

```javascript
$(document).ready(function() {
  var dataset = [100, 200, 300];

  var svg = d3.select("body").append("svg")
                              .attr("width",300)
                              .attr("height",200);                              
  var elements = svg.selectAll("rect")
                     .data(dataset);
  elements.enter().append("rect")
                   .attr("x",0)
                   .attr("y",function(d,i){return i*60;})
                   .attr("width",function(d){return d;})
                   .attr("height",50)
                   .attr("fill","steelblue");
});
```
@[9,10](x)
@[9,10,11](y - uses i (index))
@[9,10,11,12](width - uses d (data value))
@[9,10,11,12,13,14](height & fill)
@[*]
[@fa[external-link]](http://localhost/d3/d3BarChartJQ4.html)

---
@title[d3 Data Binding]
### d3 Data Binding

Let's change the number of data values in the array...

---
@title[d3 Data Binding]

```javascript
$(document).ready(function() {
  var dataset = [100, 200, 300, 400];

  var svg = d3.select("body").append("svg")
                              .attr("width",300)
                              .attr("height",200);                              
  var elements = svg.selectAll("rect")
                     .data(dataset);
  elements.enter().append("rect")
                   .attr("x",0)
                   .attr("y",function(d,i){return i*60;})
                   .attr("width",function(d){return d;})
                   .attr("height",50)
                   .attr("fill","steelblue");
});
```

[@fa[external-link]](http://localhost/d3/d3BarChartJQ5.html)


@ul[](true)
- The height and width of the 4th bar is missing
@ulend

---
@title[d3 Data Binding]

```javascript
$(document).ready(function() {
    var dataset = [100, 200, 300, 400];
  
    var svg = d3.select("body").append("svg")
    .attr("width",function(){return Math.max(...dataset)})
    .attr("height",function(){return dataset.length*60});                              
    var elements = svg.selectAll("rect")
                       .data(dataset);
    elements.enter().append("rect")
                     .attr("x",0)
                     .attr("y",function(d,i){return i*60;})
                     .attr("width",function(d){return d;})
                     .attr("height",50)
                     .attr("fill","steelblue");
  }
```
@[4-6]()
@[*]()
[@fa[external-link]](http://localhost/d3/d3BarChartJQ6.html)


---
@title[d3 Data Binding]
### D3 Exercise 3 – D3 Data Binding

[@fa[external-link]](https://github.com/noucampdotorgSSAD2021/d3/blob/main/exercises/D3Ex3.md)




---
@title[d3 Data Fetch]
### d3 Data Fetch

@ul[](true)
- Previously, our static data values were stored in an array
- d3 allows you to fetch data from numerous other sources
- For example, you can fetch:
  - JSON data
  - .CSV data
  - text
  - etc.
@ulend


---
@title[d3 Data Fetch]
### d3 Data Fetch Functions

Some d3 data fetch functions include:

@ul[](true)
- `d3.json()` - fetches JSON from specific URL
- `d3.csv()` - fetches CSV from specific URL
- `d3.text()` - fetches text from specific URL
- `d3.html()` - fetches HTML from specific URL
- others are [here](https://github.com/d3/d3-fetch/blob/master/README.md#api-reference)
- Let's start with the `d3.json()` function...
@ulend


---
@title[d3 Data Fetch]
### d3 Data Fetch

Let's get data from [http://localhost/d3/numbers.json](http://localhost/d3/numbers.json)

```javascript
[
    {"value":100},
    {"value":200},
    {"value":300}
]
```

---
@title[d3 Data Fetch]
### d3.JSON function

Provide the URL for the JSON file:

```javascript
d3.json("http://localhost/d3/numbers.json")
```

---
@title[d3 Data Fetch]
### d3.JSON function

Then get **ALL** JSON file contents:

```javascript
d3.json("http://localhost/d3/numbers.json")
  .then(function(dataset)
  {
    console.log(dataset);
  });
```
@[1](get the file data)
@[1,2-5](when you get the data print to console)
@[*]()

[@fa[external-link]](http://localhost/d3/d3JSON0jq.html)

@ul[](true)
- Let's add this to our previous solution...
@ulend


---
@title[d3 Data Fetch]
### d3.JSON function

Our HTML file `d3JSON1jq.html`:

```html
<!doctype html>
<html>
<head>
    <script src="https://code.jquery.com/jquery-3.5.1.min.js" integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" crossorigin="anonymous"></script>
    <script src="https://d3js.org/d3.v6.min.js"></script>
    <script src="d3JSON1jq.js"></script>
</head>
<body>
</body>
</html>
```

---

```javascript
$(document).ready(function() {
    var svg = d3.select("body").append("svg")
                               .attr("width",300)
                               .attr("height",200);                                  
    d3.json("http://localhost/d3/numbers.json")
        .then(function(dataset) {
        var elements = svg.selectAll("rect").data(dataset);

        elements.enter().append("rect")
                .attr("x",0)
                .attr("y",function(d,i){return i*60;})
                .attr("width",function(d){return d.value;})
                .attr("height",50)
                .attr("fill","steelblue");
    });    
});

```
@[5,6,15](get the JSON data)
@[5,6,15,7-8](bind dataset as usual)
@[5,6,15,7-8,9-14](add rectangle for each value)
@[12](d is an object, so d.value is used to get value)
@[*]()

[@fa[external-link]](http://localhost/d3/d3JSON1jq.html)


---
@title[d3 Data Fetch]
### d3.JSON function

Let's get the data from a database using PHP this time...

---
@title[d3 Data Fetch]
### d3.JSON function

`- d3JSON2.php -`
```php
<?php
$connection = mysqli_connect("localhost","root","");
mysqli_select_db($connection,"d3");
$result = mysqli_query($connection,"SELECT * FROM d3table");

$rs = array();
while($rs[] = mysqli_fetch_assoc($result)) {
}
mysqli_close($connection);
unset($rs[count($rs)-1]);  //removes a null value
print(json_encode($rs));
?>
```
@[3](database is called d3)
@[3,4](table is d3table)
@[*](returns rows as JSON data)
[@fa[external-link]](http://localhost/d3/d3JSON2.php)


---
@title[d3 Data Fetch]
### d3.JSON function

Our HTML file `d3JSON2jq.html`:

```html
<!doctype html>
<html>
  <head>
    <script src="https://code.jquery.com/jquery-3.5.1.min.js" integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" crossorigin="anonymous"></script>
    <script src="https://d3js.org/d3.v6.min.js"></script>
    <script src="d3JSON2jq.js"></script>
</head>
<body>
</body>
</html>
```

---

```javascript
$(document).ready(function() {
  var svg = d3.select("body").append("svg")
                              .attr("width",300)
                              .attr("height",200);                                  
  d3.json("http://localhost/d3/d3JSON2jq.php")
     .then(function(dataset)
  {
    var elements = svg.selectAll("rect")
                      .data(dataset);   
    elements.enter().append("rect")
                    .attr("x",0)
                    .attr("y",function(d,i){return i*60;})
                    .attr("width",function(d){return d.value;})
                    .attr("height",50)
                    .attr("fill","steelblue");        
  });
});
```
@[5,6](get data from PHP script this time)
@[*](everything else is same)

[@fa[external-link]](http://localhost/d3/d3JSON2jq.html)



---
@title[d3 Data Fetch]
### d3.csv function

Let's take this CSV file `d3table.csv` and render it with d3

```javascript
name,value
"Apples",100
"Pears",200
"Oranges",300
```

---
@title[d3 Data Fetch]
### d3.csv function

Our HTML file `d3CSV1jq.html`:

```html
<!doctype html>
<html>
<head>
  <script src="https://code.jquery.com/jquery-3.5.1.min.js" integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" crossorigin="anonymous"></script>
  <script src="https://d3js.org/d3.v6.min.js"></script>
  <script src="d3CSV1jq.js"></script>
</head>
<body>
</body>
</html>
```

---

```javascript
$(document).ready(function() {
  var svg = d3.select("body").append("svg")
                              .attr("width",300)
                              .attr("height",200);                                  
  d3.csv("http://localhost/d3/d3table.csv")
     .then(function(dataset)
  {
    var elements = svg.selectAll("rect")
                      .data(dataset);   
    elements.enter().append("rect")
                    .attr("x",0)
                    .attr("y",function(d,i){return i*60;})
                    .attr("width",function(d){return d.value;})
                    .attr("height",50)
                    .attr("fill","steelblue");        
  });
});

```
@[5,6](get data from the CSV file)
@[*](everything else is same)

[@fa[external-link]](http://localhost/d3/d3CSV1jq.html)




---
@title[d3 Data Binding]
### D3 Exercise 4 – D3 Data Fetch

[@fa[external-link]](https://github.com/noucampdotorgSSAD2021/d3/blob/master/exercises/D3Ex4.md)

