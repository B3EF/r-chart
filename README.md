# r-chart


### description
<ul>
  <li>
    create line chart , bar chart and combo chart.
  </li>
  <li>
    editable points. select point(s) and drag to change value.  
  </li>
  <li>
    developed by reactjs.
  </li>
  <li>
    responsive.
  </li>
  <li>
    customizable style.
  </li>
  <li>
    zoomable.
  </li>
  <li>
   up to 1000000 point support.
  </li>
</ul> 

### Instalation
```npm i r-chart```

### Usage

```
import react from 'react';
import RChart from "r-chart";
<RCahrt data={} x={} y={} padding={} onchange={} style={}/>
```

### Root Properties
Properties | Type | Required | Description
---------- | ---- | -------- | -----------
data | Array of objects | Required | each member of data is an object that render a sort of values(line or bars).</td>
x | Object | Required | horizontal axis configuration
y | Object | Required | vertical axis configuration


### data Properties
Properties | Type | Required | Description
---------- | ---- | -------- | -----------
stream | Array of objects | Required | Each member of stream is a point of data that have x and y properties.
type | string | default is "line" | Type of chart for this member of data("line" or "bar")
color | string | default is "#444" | Color of this member of data.
lineWidth | number(+) | default is 2 | Set width of lines in line chart.
dash | Array of 2 number | Optional | Set dashed style for lines in line chart.first number is length of fill and second number is length of empty.
pointColor | string | default is "#444" | Color of point in line chart.
width | number | default is 80 | Number between 1 and 100. width percent of bars in bar chart.
### **x** Properties
Properties | Type | Required | Description
---------- | ---- | -------- | -----------
labels | Array of strings | Required if x property of stream members is string | List of labels of horizontal axis. use when x property of stream members is string
zoom | boolean | default is false | set horizontal axis zoomable.
gridColor | string | Optional | Color of horizontal grid lines.
rotation | number | Optional | Set angle of horizontal labels.
<h3>y Properties</h3>
Properties | Type | Required | Description
---------- | ---- | -------- | -----------
zoom | boolean | default is false | set vertical axis zoomable.
gridColor | string | Optional | Color of vertical grid lines.
### Sample Configuration
```javascript
<RChart
    data={[
       {
          color:'lightgreen',type:'bar',width:60,
          stream:[
            {x:'Jan',y:0},{x:'Feb',y:4},{x:'Mar',y:0},{x:'Apr',y:3},{x:'May',y:5}
          ]
       },
      {
        lineWidth:2,color:'orange',r:4,point:true,dash:[5,3],
        stream:[
          {x:'Jan',y:0},{x:'Feb',y:4},{x:'Mar',y:0},{x:'Apr',y:3},{x:'May',y:20}
        ],
      },
    ]
    x={{
      gridColor:'#ddd',
      zoom:true,
      rotation:10,
      labels:["Jan","Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec" ],
    }}
    y={{
      gridColor:'#ddd',
      zoom:true
    }}
    padding={{top:8,right:8,bottom:50,top:20}}
    onchange={(data)=>{
      this.setState({data});
    }}
 />

<a href="https://stackblitz.com/edit/r-chart-qfx76m">See demo on stackblitz</a><br>
