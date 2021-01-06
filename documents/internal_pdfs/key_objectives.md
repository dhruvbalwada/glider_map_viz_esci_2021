# Key Objectives 
Here we document the main objectives of the project, and the key steps that will need to be completed to fulfil them. 

## Mapping 
We are planning on using Gaussian Process Regression (GPR) to map the glider data. This is the same technique as kriging, with the improvement that the parameters for the correlation functions are estimated using maximum likelihood estimation (MLE) and error estimates are also obtained. Using [GPyTorch](https://gpytorch.ai/) is a probably a good idea for this (but lets talk more). 

Here are the things that need to happen:
- Figure out how to choose correlation functions. This will require some testing and thinking. Matern functions might be a good starting point. How to account for X-Y-Z-T sampling. 
- Generate a test data set from LLC4320 to test GPyTorch, where the truth is know.
- Figure out how to sample the model like a glider.
- Once a method works on model samples, try it on glider data. 
- Do some sensitivity analysis on test data to learn how much confidence we can place on mapped glider data. 
- Can we use the 2 gliders to map data horizontally between the gliders?

>**What is one key science result that would be great to see with improved mapping?**   
    Estimation of the vertical velocities in the ocean is very challenging, since they are many orders of magnitude smaller than the horizontal velocities. Often they are estimated using the Omega equations, which require reasonable estimates of density and velocity gradients. Improved maps will result in improved estimates of gradients, and likely improved estimates on vertical velocities. These vertical velocities can then be useful to say something about the local ventilation rates. 
    Usually these estimates are obtained by using a fleet of gliders with very heavy sampling in a small region. 


## Visualization
