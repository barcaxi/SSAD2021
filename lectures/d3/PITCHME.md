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

window.onload = function() {
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


