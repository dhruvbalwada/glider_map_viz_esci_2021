# Gaussian Process Regression, Krigging, Objective Mapping

Some notes about learning GPR.

https://www.cs.toronto.edu/~duvenaud/cookbook/

http://inverseprobability.com/talks/notes/gaussian-processes.html

**References**
Also known as kriging in geophysics.

Links to some stuff online and their usefulness: 
- https://towardsdatascience.com/an-intuitive-guide-to-gaussian-processes-ec2f0b45c71d A decent and very basic idea about what GP tries to do. Also notes the pros and cons on this technique, in relation to other machine learning methods. 
- https://distill.pub/2019/visual-exploration-gaussian-processes/#DimensionSwap A very cool and detailed look at GPR, to give an intuitive feel for what goes on.
- https://yugeten.github.io/posts/2019/09/GP/ comes with a lecture video, which I found super useful. Also written as a fun read, with a cheeky style. Very useful overall to understand the math and its interpretation. 
- https://github.com/dfm/gp/blob/master/worksheet.ipynb Code on how to implement GPs in python.
- Really helpful youtube video: https://www.youtube.com/watch?v=R-NUdqxKjos Also links upto to GPytorch
- Implementation with math: https://nbviewer.jupyter.org/github/adamian/adamian.github.io/blob/master/talks/Brown2016.ipynb (found this most helpful so far: 3 April 2020)
- https://towardsdatascience.com/understanding-gaussian-process-the-socratic-way-ba02369d804


Chris Fonnesbeck
https://www.youtube.com/watch?v=xBE8qdAAj3w
https://blog.dominodatalab.com/fitting-gaussian-process-models-python/
(nice description, but a bit short on the details, which makes it hard to interpret what is going on.)

## What are different ways to estimate parameters:
- Maximum likelihood estimator, Maximum A Posteriori: https://towardsdatascience.com/a-gentle-introduction-to-maximum-likelihood-estimation-and-maximum-a-posteriori-estimation-d7c318f9d22d
- Bayesian Inference: https://towardsdatascience.com/mle-map-and-bayesian-inference-3407b2d6d4d9



Notes: 
GPRs or krigging involves a few steps. 

a) Estimate the correlation function. This can be done simply using a variogram. However, this not good enough because it makes it very hard to do any calculation this way - so it makes a lot more sense to estimate a functional form. This parameter estimation can be done using maximum likelihood estimation (MLE) or MAP approaches. 

b) If we know the correlation function (from fitting above), then it is time for prediction. This is the second step that Kriging deals with.
