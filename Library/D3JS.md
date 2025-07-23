## 📊 What is D3.js?

**D3.js** (Data-Driven Documents) is a **JavaScript library** used to create **interactive, dynamic, and customizable data visualizations** using HTML, SVG, and CSS.

> Unlike chart libraries (like Chart.js), D3 gives you **full control** over every visual element, enabling **custom, complex, and animated data visualizations**.

---

## 🌐 Why Use D3.js?

✅ Create any chart or visual — line, bar, pie, scatter, tree, heatmap, choropleth, etc.
✅ Bind data directly to DOM elements
✅ Powerful transitions and animations
✅ Works with **SVG, Canvas**, and even HTML
✅ Highly customizable and extensible

---

## 📦 How to Use D3.js

### Option 1: Use via CDN (in HTML)

```html
<script src="https://d3js.org/d3.v7.min.js"></script>
```

### Option 2: Use via NPM (React, Node.js)

```bash
npm install d3
```

Then import in your JS:

```js
import * as d3 from 'd3';
```

---

## 🧠 D3 Core Concepts

| Concept               | Description                                              |
| --------------------- | -------------------------------------------------------- |
| **Selections**        | Select DOM elements to bind/manipulate                   |
| **Data Binding**      | Connect your data to those DOM elements                  |
| **Enter/Update/Exit** | Dynamically update the DOM when data changes             |
| **Scales**            | Map data values to screen space (x/y axes, colors, size) |
| **Axes**              | Generate beautiful axes automatically                    |
| **Transitions**       | Animate changes smoothly                                 |

---

## 🟢 Example 1: Basic Bar Chart

### HTML + CSS:

```html
<div id="chart"></div>
<style>
  .bar {
    fill: steelblue;
  }
</style>
```

### JavaScript:

```js
const data = [10, 15, 20, 25, 30];

const svg = d3.select("#chart")
  .append("svg")
  .attr("width", 300)
  .attr("height", 150);

svg.selectAll("rect")
  .data(data)
  .enter()
  .append("rect")
  .attr("class", "bar")
  .attr("x", (d, i) => i * 60)
  .attr("y", d => 150 - d * 4)
  .attr("width", 40)
  .attr("height", d => d * 4);
```

---

## 🧬 Core Modules in D3

* **d3-selection** → `.select()`, `.selectAll()` for DOM elements
* **d3-scale** → `scaleLinear()`, `scaleBand()` for data → pixels
* **d3-axis** → `axisBottom()`, `axisLeft()` for axis generation
* **d3-shape** → `line()`, `arc()`, `area()` for drawing paths
* **d3-transition** → Smooth animation with `.transition()`
* **d3-array** → Sort, filter, summarize data
* **d3-fetch** → Load CSV, JSON, etc.

---

## 📈 Example 2: Line Chart

```js
const data = [
  { x: 0, y: 20 },
  { x: 1, y: 35 },
  { x: 2, y: 40 },
  { x: 3, y: 50 },
];

const width = 300;
const height = 150;

const svg = d3.select("#chart")
  .append("svg")
  .attr("width", width)
  .attr("height", height);

const x = d3.scaleLinear().domain([0, 3]).range([0, width]);
const y = d3.scaleLinear().domain([0, 60]).range([height, 0]);

const line = d3.line()
  .x(d => x(d.x))
  .y(d => y(d.y));

svg.append("path")
  .datum(data)
  .attr("fill", "none")
  .attr("stroke", "blue")
  .attr("d", line);
```

---

## 🎨 Scales and Axes

```js
const xScale = d3.scaleLinear().domain([0, 100]).range([0, 500]);
const yScale = d3.scaleLinear().domain([0, 100]).range([500, 0]);

const xAxis = d3.axisBottom(xScale);
const yAxis = d3.axisLeft(yScale);

svg.append("g").attr("transform", "translate(0,500)").call(xAxis);
svg.append("g").call(yAxis);
```

---

## 🔄 Transitions (Animation)

```js
svg.selectAll("rect")
  .transition()
  .duration(1000)
  .attr("height", d => d * 10)
  .attr("y", d => 150 - d * 10);
```

---

## 📚 D3 Charts You Can Create

| Chart Type     | Modules Used                          |
| -------------- | ------------------------------------- |
| Bar Chart      | `d3-scale`, `d3-selection`, `d3-axis` |
| Line Chart     | `d3-shape`, `d3-scale`, `d3-axis`     |
| Pie Chart      | `d3-pie`, `d3-arc`, `d3-shape`        |
| Tree/Hierarchy | `d3-hierarchy`, `d3-tree`             |
| Force Layout   | `d3-force`                            |
| Heatmap        | `d3-scale`, `d3-array`, `d3-color`    |
| Geo/Map Charts | `d3-geo`, `d3-geoPath`                |

---

## 💡 When to Use D3.js?

Use D3 when you need:

* Full control over visuals
* Dynamic or real-time data
* Custom animations and interactivity
* Data storytelling with visuals

If you just need quick charts with defaults, consider simpler libraries like:

* **Chart.js**
* **Recharts (React)**
* **ECharts**
* **Highcharts**

---

## 📘 Resources

* 🌐 [Official Site](https://d3js.org/)
* 📚 [Full API Docs](https://github.com/d3/d3/blob/main/API.md)
* 💡 [D3 Gallery (examples)](https://observablehq.com/@d3/gallery)
* 📘 [Full Course by Curran Kelleher (YouTube)](https://www.youtube.com/watch?v=_8V5o2UHG0E)

---
