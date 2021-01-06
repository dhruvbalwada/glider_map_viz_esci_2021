# Mapping and visualizing the ocean using scattered glider observations 
## A toolset to investigate submesoscale ventilation

Project lead: [Dhruv Balwada](https://dhruvbalwada.github.io/)  
Data science lead: [Rob Fatland](https://escience.washington.edu/people/rob-fatland/)  
Stakeholder: [Alison Gray](https://alisonrgray.com/)  

Codes and notes about the glider mapping and visualizing project as part of the [e-science winter incubator 2021](https://escience.washington.edu/get-involved/incubator-programs/overview/). 


### Project Description
Since the industrial revolution 25-30% of the human-created carbon and 90% of the excess heat in the earth system has been sequestered into the deep ocean. A lot of this tracer (eg heat, carbon, oxygen etc) transport from the surface into the interior takes place synoptically in narrow filaments (submesoscale flows), which then merge and mix together at depth to result in a mean increase in amount of tracer at depth. To study the dynamics of these structures we need to make observations that span the depth of the water column and are collected at scales of a few kms and hours. This is possible using [gliders](https://oceanservice.noaa.gov/facts/ocean-gliders.html), which profile the ocean on a zig-zag path as the move up and down through the water column. 

The goal of this project is to develop tools to better explore these glider data sets. In particular we want to:
- Develop a mapping algorithm to map from the scattered space-time observations collected by the glider to a grid, which is easier to visualize and conduct analysis on, and also respects the structural properties of the fields.
- Develop a visualization dashboard for the glider, which allows for an interactive analysis of the data - eg colocate multiple variables to get a deeper insight into how observed structures might be generated.

>![](https://i.imgur.com/LHjmsUn.png)
Figure: An example of a temperature section collected by a glider showing the zig-zag sampling, and examples of temperature filaments extending across depth. 