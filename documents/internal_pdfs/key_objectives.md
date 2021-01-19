# Key Objectives 
Here we document the main objectives of the project, and the key steps that will need to be completed to fulfil them. 

## Mapping 
We are planning on using [Gaussian Process Regression (GPR)](https://github.com/dhruvbalwada/glider_map_viz_esci_2021/blob/main/documents/internal_pdfs/GPR_references.md) to map the glider data (*any other techniques we should try?*). This is the same technique as kriging, with the improvement that the parameters for the correlation functions are estimated using maximum likelihood estimation (MLE) and error estimates are also obtained. Using [GPyTorch](https://gpytorch.ai/) is a probably a good idea for this (but lets talk more). 

Here are the things that need to happen:
- Figure out a good library to use, incase we don't want to go with GPyTorch.
- Figure out how to choose correlation functions. This will require some testing and thinking. Matern functions might be a good starting point. How to account for X-Y-Z-T sampling? 
- Generate a test data set from a high-resolution ocean simulation (LLC4320) to test GPyTorch based mapping; a dataset where the truth is know.
- Figure out how to sample the model like a glider.
- ... (probably more things will crop up here)
- Once a method works on model samples, try it on glider data. 
- Do some sensitivity analysis on test data to learn how much confidence we can place on mapped glider data. 
- Can we use the 2 gliders to map data horizontally between the gliders?

>**What is one key science result that would be great to see with improved mapping?**   
    Estimation of the vertical velocities in the ocean is very challenging, since they are many orders of magnitude smaller than the horizontal velocities. Often they are estimated using the Omega equations, which require reasonable estimates of density and velocity gradients. Improved maps will result in improved estimates of gradients, and likely improved estimates on vertical velocities. These vertical velocities can then be useful to say something about the local ventilation rates. 
    Usually these estimates are obtained by using a fleet of gliders with very heavy sampling in a small region. An example of estimating some gradient properties is [here](https://www.mdpi.com/2311-5521/5/3/159/htm), where they use a cluster of drifters to estimate surface kinematic properties. I think we can do better. 


## Visualization
We are planning on using [HoloViz](https://holoviz.org/) to develop an interactive dashboard. We have a prototype that sort of does somethings, but we need to think more about what we want exactly. Here are some key things that need to happen: 

- The viz is currently done using a gridded data set, where linear interpolation has been done. We need to improve on this. 
- Integrate more variables measured by gliders into dashboard.
- An easy way to switch back and forth between distance and time axis. 
- Is the current plotting taking place optimally? or are we replotting frames that are not needed (wasting resources)?
- Zooming and panning often resets different panels, would be nice to fix that. 
- An easy way to switch colorbars. 
- Should we incorporate an option to save the state (maybe just a figure generated from the state of the dashboard)? Incase the user finds an interesting feature that they would like to remember to explore later. 
- Are there other surface variables we can tap into? Last I checked the region was very cloudy during the glider mission - implying very coarse SST and chlorophyll. 
- Can we host the dashboard in a place for others to use? 
- What is a good way to share the dashboard that allows others to easily adopt it?


>**What is one key science result that would be great to get insight from this platform?**   
>The ease of exploring data would be essential to gain a deeper understanding of the data much faster. For the glider data at hand we will use the to explore the structure and size of the anomalies.