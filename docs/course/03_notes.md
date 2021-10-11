---
template: overrides/main.html
---

# Frontend

**Step I. Resume: <br>**
Let's continue where we left off from the frontend setup. If the React project is off then execute the project!

```
tigergraph-fullstack$ cd front
front$ npm start

Compiled successfully!

You can now view front in the browser.

  Local:            http://localhost:3000
  On Your Network:  http://192.168.50.45:3000

Note that the development build is not optimized.
To create a production build, use npm build.
```

Now, we can use a browser to open the project with URL: [http://localhost:3000](http://localhost:3000)
![react-hello-world](img/react-hello-world.png)

**Step II. Removeing the Hello World: <br>**
The npx creates the React project with the files and folder structure. Let's open the file 'App.js' located in '/tigergraph-fullstack/front/src/App.js'

![react-folder-structure](img/react-folder-structure.png){: style="height:300px;width:240px"}

Replace the code over the current existing code in 'App.js'.

```
import './App.css';

import React, { Component } from 'react';

class App extends Component {
  render() {
    return (
      <div className="App">
        <h1>GSQL Query: listPatients_Infected_By(2000000205)</h1>
      </div>
    );
  }
}

export default App;
```

We replaced the React Functional Component with React Class Component. In addition, we added a h1 tag and giving div tag a class name called 'App' which is from the import of 'App,css'.

Afterward the [http://localhost:3000](http://localhost:3000) will show this.

![rt-rm-hw](img/rt-rm-hw.png){: style="border-style: inset;"}

From the header/h1 information, we are going to create a graph showing a list of patients infected by the vertex id of 2000000205.

**Step II. Libraries: <br>**
Let's import all the libraies inside the 'App.js' on first two lines.

```
import axios from 'axios';
import G6 from '@antv/g6';
```

[AntV G6](https://antv.vision/en) will be used in this tutorial which is a new generation of data visualization solution from Ant Group. In addition, Axios provides a small package with a very extensible interface. [Learn more](https://axios-http.com/)

**Step III. Loading Data at front: <br>**
Three key points to cover from loading the data at frontend which are 1) React constructor, 2) React life Cycle, and 3) Axios (HTTP request).
<br/>
<br/>1) The React constructor is a method that's automatically called during the creation of an object from a class. Therefore, it is used to bind event handlers to the components. In other words, we will use to create a state to store data object.

```
constructor() {
super();
this.state = { data: [] };
}
```

<br/>2) Life cycle in particular of componentDidMount() method runs after the component output has been rendered to the DOM.

```
componentDidMount() {}
```

<br/>3) Axios is a simple promise based HTTP client which use in React to make request from the FastAPI endpoint.

```
axios.get('http://127.0.0.1:8000/listPatients_Infected_By').then((res) => {
    if (res.status === 200) {
    }
    })
    .catch((err) => {
    console.error(err);
    });
```

**The entire App.js: <br>**

```
import axios from 'axios';
import G6 from '@antv/g6';
import './App.css';
import React, { Component } from 'react';
class App extends Component {
  constructor() {
    super();
    this.state = { data: [] };
  }
  componentDidMount() {
    axios
      .get('http://127.0.0.1:8000/listPatients_Infected_By')
      .then((res) => {
        if (res.status === 200) {
        }
      })
      .catch((err) => {
        console.error(err);
      });
  }
  render() {
    return (
      <div className="App">
        <h1>GSQL Query: listPatients_Infected_By(2000000205)</h1>
      </div>
    );
  }
}
export default App;
```

The axios is making the request to 'http://127.0.0.1:8000/listPatients_Infected_By' and it is executed inside the componentDidMount method scope; Once the component is rendered onto the DOM then the life cycle executed the code inside of itself! The endpoint of 'http://127.0.0.1:8000/listPatients_Infected_By' is requested by axios, and it will be detail covered on its implemenataion in the next chapter.

> Let's assume the endpoint is created at this time.

**Step IV Data preparing with AntV G6: <br>**
Great job! The last step of the frontend part is to prepare the response data, which is a json format.The listPatients_Infected_By endpoint is a GET method API, and it is requested by the Axios of HTTP based libray. Data preparation is only executed when the request data status responds with a message code '200' as a successful message.

> Explanation on AntV G6 Implemenataion line by line:

```
// load the response data to component state
this.setState({ data: res.data });
// store the container id from the DOM
const container = document.getElementById('container');
// assign either current browser scoll width or 1280 pixel
const width = container.scrollWidth || 1280;
// assign either current browser scoll height or 1280 pixel
const height = window.height || 800;

// Once the data is set in the state and gather the DOM window dimension let's initiated a graph using Antv G6
const graph = new G6.TreeGraph({
// assign container name, width, height, and link display position
container: 'container',
width,
height,
linkCenter: true,
// inside the modes assign properties with collapse-expland, drag-canvas, zoom-cavas, drag-node, activate-relations,
modes: {
    default: [
    {
        type: 'collapse-expand',
        onChange: function onChange(item, collapsed) {
        const data = item.get('model');
        data.collapsed = collapsed;
        return true;
        },
    },
    'drag-canvas',
    'zoom-canvas',
    'drag-node',
    'activate-relations',
    ],
},
// lastly assign default node sid and the graph's layout
defaultNode: {
    size: 55,
},
layout: {
    type: 'dendrogram',
    direction: 'RL',
    nodeSep: 20,
    rankSep: 400,
    radial: true,
},
});

// tra
graph.node(function (node) {
return {
    label: `${node.name.slice(0, 3)}\n${node.name.slice(3)}`,
    size: node.children.length ? 52 : 50,
};
});

graph.data(this.state.data);
graph.render();
graph.fitView();
graph.get('canvas').set('localRefresh', false);

graph.on('node:click', (evt) => {
const nodeItem = evt.item;
if (!nodeItem) return;
const item = nodeItem.getModel();
if (item.url) {
    window.open(item.url);
}
});

if (typeof window !== 'undefined')
window.onresize = () => {
    if (!graph || graph.get('destroyed')) return;
    if (
    !container ||
    !container.scrollWidth ||
    !container.scrollHeight
    )
    return;
    graph.changeSize(container.scrollWidth, container.scrollHeight);
};
```
