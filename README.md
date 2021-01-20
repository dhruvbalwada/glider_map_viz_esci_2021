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

### Experiment and Data Sketch

The field data are from a Lagrangian drift experiment conducted in 2019 in the southern ocean.
Two gliders designated "*659*" and "*660*" were deployed
for 88 days April 28 - July 24, 2019 in proximity to an ARGO BioGeoChem drifter.
This coincides with winter in the southern hemisphere. 
The deployment was over the Southwestern Indian Ridge (SWIR) 
southeast of Africa.
The two gliders executed approximately six dive/ascent cycles per day and were episodically 
re-tasked by scientists aboard the monitoring research vessel in response to evolving conditions.


The ARGO drifter cycled through the water column every five days. 
This consisted of a long 'park' interval at 1000 meters, descent to 2000 meters, ascent to the surface, 
data telemetry via satellite ('20 minutes'), and a descent back to 1000 meters for the next park.  
Satellite altimetry data were collected for this study, consisting of three scalar fields over the
time extent of the experiment. These are sea surface height (SSH), sea surface height anomaly (SSHA) 
and a transport characterization parameter called FSLE that is derived from surface velocity 
vector fields. FSLE abbreviates 'Finite-Size Lyapunov Exponent' and indicates trajectory
separation rate for two surface drifters initially close to one another.
