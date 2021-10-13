---
template: overrides/main.html
---

## Step I. Exploring the solution dataset

To do this, open GraphStudio by going to "Applications Icon" and clicked on "GraphStudio" from the dropdown.

![gs](img/gs.png)

## Step II. Select MyGraph

In the tab that opens, click "Global View" in the top left corner then select "MyGraph" from the dropdown to enter the MyGraph graph.

![gs-mygraph](img/gs-mygraph.png)

## Step III. Data loading

To do this, click the “Load Data” tab then press the play button with the hover value of “Start/Resume loading.”

![gs-data-loading](img/gs-data-loading.png)

Click on the contune to proceed the loading.

![gs-data-loading-confirmation](img/gs-data-loading-confirmation.png)

## Step IV. GSQL Queries

Perfect! Next, we’ll install all the queries. To do this, go to the “Write Queries” tab and press the box with an up arrow.

![gs-query-install](img/gs-query-install.png)

![gs-query-install-confirmation](img/gs-query-install-confirmation.png)

This tutorial will use the exiting query to demonstrate the fullstack. In this case, the GQSL query used in the tutorial is "listPatients_Infected_By".

![gs-gsql-infectedByPatient](img/gs-gsql-infectedByPatient.png)

This query finds the patient infected by the input of "Patient Vertex ID" (2000000205). Therefore, the query outputs a list of Infected_Patients by the Patient Vertex ID (2000000205).

![gs-gsql-infectedByPatient-output](img/gs-gsql-infectedByPatient-output.png)

In addition, GraphStudio allows create your own custom GSQL queries!
If you want to learn more about TigerGraph Cloud, check out [this blog](https://www.tigergraph.com/blog/getting-started-with-tigergraph-3-0/).
