# Key Objectives 
Here we document the main objectives of the project, and the key steps that will need to be completed to fulfil them. 

## Mapping 
We are planning on using [Gaussian Process Regression (GPR)](https://github.com/dhruvbalwada/glider_map_viz_esci_2021/blob/main/documents/internal_pdfs/GPR_references.md) to map the glider data (*any other techniques we should try?*). This is the same technique as kriging, with the improvement that the parameters for the correlation functions are estimated using maximum likelihood estimation (MLE) and error estimates are also obtained. Using [GPyTorch](https://gpytorch.ai/) is a probably a good idea for this (but lets talk more). 

Here are the things that need to happen:
- Figure out a good library to use, incase we don't want to go with GPyTorch.
- Figure out how to choose correlation functions. This will require some testing and thinking. Matern functions might be a good starting point. How to account for X-Y-Z-T sampling? 
- Generate a test data set from a high-resolution ocean simulation (LLC4320) to test GPyTorch based mapping; a dataset where the truth is know.
- Figure out how to sample the model like a glider.
- How do we deal with the large number of points from the glider?
- ... (probably more things will crop up here)
- Once a method works on model samples, try it on glider data. 
- Do some sensitivity analysis on test data to learn how much confidence we can place on mapped glider data. 
- Can we use the 2 gliders to map data horizontally between the gliders?

>**What is one key science result that would be great to see with improved mapping?**   
    Estimation of the vertical velocities in the ocean is very challenging, since they are many orders of magnitude smaller than the horizontal velocities. Often they are estimated using the Omega equations, which require reasonable estimates of density and velocity gradients. Improved maps will result in improved estimates of gradients, and likely improved estimates on vertical velocities. These vertical velocities can then be useful to say something about the local ventilation rates. 
    Usually these estimates are obtained by using a fleet of gliders with very heavy sampling in a small region. An example of estimating some gradient properties is [here](https://www.mdpi.com/2311-5521/5/3/159/htm), where they use a cluster of drifters to estimate surface kinematic properties. I think we can do better. 


## Visualization

We want to create an interactive dashboard for visualizing glider data using holoviz. A prototype is here: https://github.com/dhruvbalwada/glider-panel-demo. Increasing the ease with which we can interact with the data can help discovery.

The dashboard has two parts: 
- A X-Y map with the glider track, and some additional properties plotted for context. 
- A depth vs time (or distance) plot of the glider measurements along the vertical axis.

#### Requirements for the two parts:

General requirements for both: 
- Switch to a class based approach for the code, as it potentially make a lot of other things easier.
- Have options to switch colormaps and color ranges interactively. 
- Make sure that the entire plot is only replotted when needed, to ensure a smooth interaction.
- Right now zooming and panning often resets different panels, would be nice to keep zoom levels.
- Have a way to save state, so that when returning to the dashboard the exact options as a previous session can be loaded.
- Atleast have options to save images. 
- ~~Can we host the dashboard in a place for others to use?~~ 
- What is a good way to share the dashboard that allows others to easily adopt it?: Improve documentation in notebooks and scripts so that other users with their own data sets can easily incorporate their own data sets into it.

The horizontal map: 
- Have an option to look a the bathymetry. 
- Currently the SSH, FSLE or other fields being plotted have to be manually downloaded and manipulated before they are put into the dashboard. Is this the best approach? 
- Can some of these fields be automatically accessed, rather than having to manually download them first.

The vertical map: 
- Add other variables measured by the glider into the list of variables. 
- Add ability to toggle between anomaly and full fields. Should this be done before hand and variables be saved? 
- Add an option to toggle the horizontal axis between time and along track distance.
- Have different options for interpolation. Currently done using linear interpolation, but have an option for GPs when first part is finished.
