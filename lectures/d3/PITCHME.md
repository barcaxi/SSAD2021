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

[@fa[external-link]](https://github.com/noucampdotorgSSAD2021/d3/blob/main/exercises/D3Ex2.md)



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
- others are [here](https://github.com/d3/d3-fetch/blob/main/README.md#api-reference)
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

[@fa[external-link]](https://github.com/noucampdotorgSSAD2021/d3/blob/main/exercises/D3Ex4.md)




---
@title[Contents]
### Contents

@ol[](false)
- What is D3?
- SVG
- d3 Setup
- d3 Bar Chart
- d3 Data Binding
- **d3 Scaling**
@olend


---
@title[d3 Scaling]
### D3 Scaling

> Scaling is the process of making chart data fit the space provided

@ul[](true)
- For example...
@ulend

---
@title[d3 Scaling]
### D3 Scaling

![](images/d3scale1.png)

@ul[](true)
- The `<svg width=600>`
- But the largest bar is `300`
- We can use **linear scaling** to use all space provided...
@ulend


---
@title[Linear Scaling]

Our code so far
```javascript
$(document).ready(function() {
  var dataset = [100, 200, 300];
  var svg = d3.select("body").append("svg")
                              .attr("width",600)
                              .attr("height",170);                              
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
@[2](largest value is 300)
@[2,4](width is 600)
@[2,4,11](rect width taken from dataset is not scaled)
@[*]()

[@fa[external-link]](http://localhost/d3/d3scale1JQ.html)

---
@title[Linear Scaling]
### Linear Scaling

@ul[](true)
- We need to use the ``d3.scaleLinear()`` function 
- Linear values go from ``-n..n``
- All scales need to specify two values:
  - a domain (data values)
  - a range (pixel values)
- For example...
@ulend

---

```javascript
$(document).ready(function() {
  var dataset = [100, 200, 300];
  var svg = ...;
  var elements=...;
  var w = d3.scaleLinear()
             .domain([0,300])
             .range([0,600]);
  elements.enter().append("rect")
                   .attr("x",0)
                   .attr("y",function(d,i){return i*60;})
                   .attr("width",function(d){return w(d);})
                   .attr("height",50)
                   .attr("fill","steelblue");
});
```
@[5](w is a reference to our scaling)
@[5](we're using a linear scale)
@[2,5,6](the domain is the min .. max range of data values)
@[2,5,6,7](the range is the min .. max range of svg pixel values)
@[2,5,6,7,11](our function w() is applied to each d value)
@[*]()

[@fa[external-link]](http://localhost/d3/d3scale2JQ.html)


---
@title[d3 Linear Scaling]
### D3 Exercise 5 – D3 Linear Scaling

[@fa[external-link]](https://github.com/noucampdotorgSSAD2021/d3/blob/main/exercises/D3Ex5.md)



---
@title[Contents]
### Contents

@ol[](false)
- What is D3?
- SVG
- d3 Setup
- d3 Bar Chart
- d3 Data Binding
- d3 Scaling
- **d3 Path**
@olend


---
@title[Path]
### Path

@ul(true)
- Paths are important in D3
- A path is essentially a @size[1.5em](line)
- Those lines can be 
  - curved
  - straight
  - filled
  - open 
  - closed 
- Paths are needed to create advanced graphics in D3
@ulend


---
@title[Path]
### Path

@ul[](false)
- We've seen how SVG elements need several mandatory attributes:
@ulend

```html
<line x1='0' y1='0' x2='200' y2='200' 
                    stroke='black' stroke-width='2' />
```
@[1](x1, y1, x2, y2 are mandatory)
@[*]()

---
@title[Path]
### Path

@ul[](false)
- `path` has one mandatory attribute:
@ulend

```html
<path d="M0 0 L100 0 L100 100 L0 100 Z" />
```

@ul[](true)
- `d` (or data)
- but `d` could have 100's or 1000's of points
- let's draw something...
@ulend


---
@title[Path]
### Path

```html
<path d="M0 0 L100 0 L100 100 L0 100 Z" />
```
draws this:

![](images/path1.png)


@ul[](true)
- another example...
@ulend


---
@title[Path]
### Path

```html
<path d="M0 100 L50 0 L100 100 Z" stroke='red' fill='blue' />
```
draws this:

![](images/path2.png)


@ul[](true)
- Path commands...
@ulend


---
@title[Path Commands]
### Path Commands

```html
<path d="M0 100 L50 0 L100 100 Z" stroke='red' fill='blue' />
```

@ul[](false)
- There are quite a few [path commands](https://www.w3schools.com/graphics/svg_path.asp):
  - M = moveto
  - L = lineto
  - Z = closepath
  - C = curveto, etc.
@ulend
@ul[](true)
- Uppercase letter indicates coordinates have  **absolute** position
- Lowercase letter indicates coordinates have  **relative** position...

---
@title[Path]
### Path

```html
<path d="M0 0 l 100 0 l 0 100 l -100 0 Z" />
```
draws this:

![](images/path1.png)



---
@title[d3 Path]
### D3 Exercise 6 – D3 Path - Part 1

[@fa[external-link]](https://github.com/noucampdotorgSSAD2021/d3/blob/main/exercises/D3Ex6.md)


---
@title[Contents]
### Contents

@ol[](false)
- What is D3?
- SVG
- d3 Setup
- d3 Bar Chart
- d3 Data Binding
- d3 Scaling
- d3 Path
- **d3 Generators**
@olend  

---
@title[Generators]
### Generators

@ul[](true)
- Paths can start to get complex very quicky
- We'll use @size[1.5em](generators) to help
- Let's see an example...
@ulend


---
@title[Path Generators]
### Path Generators

Using SVG `<line>`
```html
<svg width="300" height="200">
  <line x1="0" y1="0" x2="50" y2="50" stroke="blue" />
  <line x1="50" y1="50" x2="100" y2="0" stroke="blue" />
  <line x1="100" y1="0" x2="150" y2="50" stroke="blue" />
  <line x1="150" y1="50" x2="200" y2="0" stroke="blue" />
</svg>
```

![](images/path3.png)

---
@title[Path Generators]
### Path Generators

Using SVG `<path>`
```html
<svg width="300" height="200">
  <path d="M0 0 L50 50 L100 0 L150 50 L200 0" 
        stroke="blue" fill='none' />
</svg>
```

![](images/path3.png)


---
@title[Path Generators]
### Path Generators

@ul[](true)
- All generators automatically create the `d` attribute values for `<path>`
- Let's use the D3 line generator `d3.line()` first...
@ulend


---
@title[Path Generators]
<!-- ### Path Generators -->

Put the data coordinates into an array

```javascript
var dataset = [ {x: 0, y: 0},
                {x: 50, y: 50},
                {x: 100, y: 0},
                {x: 150, y: 0},
                {x: 200, y: 0}
              ];

```

---
@title[Path Generators]

- Let's declare the line generator function

```javascript
var dataset = [ {x: 0, y: 0}, {x: 50, y: 50}, ... ];

var line = d3.line()
              .x()
              .y();
```
@ul[](true)
- `d3.line()` is the line generator
- `line` is a function reference
- we'll provide it the appropriate `x` and `y` values...
@ulend


---
@title[Path Generators]

- Get the `x,y` values from the `dataset` objects

```javascript
var dataset = [ {x: 0, y: 0}, {x: 50, y: 50}, ... ];

var line = d3.line()
              .x(function(d){
                   return d.x;
                 }
              )
              .y(function(d) {
                   return d.y;
                 }
              );
```

@ul[](true)
- Let's use the `line` generator function to draw our lines...
@ulend


---
@title[Path Generators]

- Call our `line` generator function with `dataset`

```javascript
var dataset = [ {x: 0, y: 0}, {x: 50, y: 50}, ... ];

var line = d3.line().x(function(d){
                         return d.x; })
                    .y(function(d) {
                         return d.y; });

var svg = d3.select("#mysvg");
svg.append("path")
    .attr('d',line(dataset))
    .attr('fill','none')
    .attr('stroke','blue');
```
@[1](Dataset of coordinates)
@[1,3-6](Declare line generator)
@[1,3-6,8](Get a reference to a svg element)
@[1,3-6,8,9-12](Use the generator to create d attribute values)
@[*]()

[@fa[external-link]](http://localhost/d3/d3lineGeneratorJQ.html)


---
@title[Path Generators]
### Path Generators


@ul[](true)
- We could also use the generator to draw curved lines...
@ulend


---
@title[Path Generators]


```javascript
var dataset = [ {x: 0, y: 0}, {x: 50, y: 50}, ... ];

var line = d3.line().x(function(d){
                         return d.x; })
                    .y(function(d) {
                         return d.y; })
                    .curve(d3.curveCardinal);

var svg = d3.select("#mysvg");
svg.append("path")
    .attr('d',line(dataset))
    .attr('fill','none')
    .attr('stroke','blue');
```
@[7]()
@[*]()

[@fa[external-link]](http://localhost/d3/d3lineGeneratorJQ.html)

See more about types of curves [here](https://github.com/d3/d3-shape/blob/master/README.md#curves)



---
@title[d3 Path]
### D3 Exercise 6 – D3 Path - Part 2

[@fa[external-link]](https://github.com/noucampdotorgSSAD2021/d3/blob/master/exercises/D3Ex6.md)



---
@title[Path Generators]
### Path Generators


@ul[](true)
- D3 has lots of other generators:
  - area
  - arc
  - histogram
  - line
  - pie
  - stack
  - etc.
- See the [API](https://github.com/d3/d3/blob/master/API.md) for more info
- Let's have a look at `d3.area()`...
@ulend

---
@title[Path Generators]
### Area Generator

- An area chart for these values `5,22,28,42,53,61,52,36,38,34,40,19,23,20,...`

![](images/path4.png)


---
@title[Area Generator]
### Area Generator

Put the data coordinates into an array

```javascript
var dataset = [5,22,28,42,53,61,52,36,
               38,34,40,19,23,20,13,5,
               5,7,6,1,1,2,1];

```

---
@title[Path Generators]

- Let's declare the area generator function

```javascript
var dataset = [5,22,28,42,53,61,52,36, ...];

var area = d3.area()
              .x()
              .y0()
              .y1();              
```

@ul[](true)
- `d3.area()` needs 2 _y_ values
  - `y0` sets value of the lower line (usually flat)
  - `y1` sets value of the upper line 
- Let's provide the `y` values...
@ulend


---
@title[Path Generators]

```javascript
var dataset = [5,22,28,42,53,61,52,36, ...];

var height = $("#svg").attr('height');
var area = d3.area()
              .x()
              .y0(height)
              .y1(function(d) {
                return height-d;
              });
```

@ul[](true)
- `y0` is `<svg>` height 
- `y1` is current value from `dataset`
- Let's provide the `x` values...
@ulend


---
@title[Path Generators]


- The `x` value uses the array index value & a spacing value

```javascript
var dataset = [5,22,28,42,53,61,52,36, ...];

var svg = d3.select("#mysvg");
var height = $("#svg").attr('height');
var area = d3.area()
              .x(function(d,i){ 
                   return i*10;
                 })
              .y0(height)
              .y1(function(d) {
                return height-d;
              });
svg.append("path")
    .attr('d',area(dataset));
```

@ul[](true)
- Let's use the `area` generator function to draw our chart...
@ulend

---
@title[Path Generators]

```javascript
var dataset = [5,22,28,42,53,61,52,36, ...];

var svg = d3.select("#mysvg");
var height = $("#svg").attr('height');
var area = d3.area()
              .x(function(d,i){ 
                   return i*10;
                 })
              .y0(height)
              .y1(function(d) {
                return height-d;
              });
svg.append("path")
    .attr('d',area(dataset));
```
@[1](Dataset of coordinates)
@[1,3](Get reference to svg)
@[1,3,4](Get svg height)
@[1,3,4,5-12](Declare the area generator)
@[1,3,4,5-12,13-14](Use the generator to create d attribute values)
@[*]()

[@fa[external-link]](http://localhost/d3/d3areaGenerator.html)


---
@title[d3 Path]
### D3 Exercise 6 – D3 Path - Part 3

[@fa[external-link]](https://github.com/noucampdotorgSSAD2021/d3/blob/main/exercises/D3Ex6.md)

