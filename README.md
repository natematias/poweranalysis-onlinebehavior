# Choosing Sample Sizes and Estimators in Studies of Online Behavior
J. Nathan Matias ([natematias.com](https://natematias.com)) ([@natematias](https://twitter.com/natematias))
January 7, 2016

In my roles at Princeton University and CivilServant, I often conduct and teach students how to conduct power analyses of experiments. In this process, researchers state their assumptions about a study and what they want to be able to observe and work from those assumptions to make decisions about the study based on what is statistically-possible:
* deciding between different kinds of designs (what to measure, how many arms, comparisons, etc)
* deciding between different kinds of estimators
* deciding what sample size to use

In September 2018, I wrote a blog post about [estimating counts of events in behavioral product testing](https://medium.com/@natematias/estimating-counts-of-events-in-behavioral-product-testing-e3b68f6143e2). Since then, I have learned how to use [DeclareDesign](http://declaredesign.org/), software for designing and evaluating study designs, including power analyses. This followup notebook continues what I began in that post, by more systematically comparing linear, poisson, and negative binomial estimators using simulated parameters based on  a real study I conducted in 2016.

I focused on these estimators because studies of online behavior usually include count outcomes with a very specific characteristic that incidents are not independent: things that receive a higher count of incidents tend to attract even more incidents. For example, a Facebook post with more likes will be seen by more people and have a higher rate of likes than a post with fewer likes. We see this pattern with likes, retweets, the number of comments in a discussion, the number of donations to a charitable activity, and many other online phenomena.

This example will exclusively focus on count outcomes. Mathematics in the utility functions are drawn from:
*  Long, J. Scott. 1997. [Regression Models for Categorical and Limited Dependent Variables](https://us.sagepub.com/en-us/nam/regression-models-for-categorical-and-limited-dependent-variables/book6071). 1 edition. Thousand Oaks: SAGE Publications, Inc.

I am grateful to my fellow postdoc [Jasper Cooper](http://jasper-cooper.com/) for presenting to the Paluck Lab last fall about how to use DeclareDesign, and to Neal Fultz, for [generously answering my questions on the DeclareDesign forum](http://discuss.declaredesign.org/t/subsetting-errors-in-a-glm-nb-multi-arm-experiment/60).

---


# LICENSE

Copyright 2019 J. Nathan Matias

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
