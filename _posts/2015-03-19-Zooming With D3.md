---
layout:     post
title:      Zooming with D3
summary:    Exploring various properties of Zooming with D3
categories: projects
---

D3 has some built in zoom beahvior, but I haven't used it yet. Today's goal is to get to know zooming: what parameters are available, how they work, and any other tips and tricks. 

To start, there is [geometric zooming](http://bl.ocks.org/mbostock/3680999) and [semantic zooming](http://bl.ocks.org/mbostock/3680957In ). In geometric, the objects get larger as if you're getting closer to them.  In semantic, they stay the same size but are just further apart when you zoom in. I'm solving for having too many points close together, so I'm going to go for semantic zooming.  

In this example, you're zooming in on both axis equally. I'm hoping to zoom on the x-axis only, since x-axis in my project is time and I want to see the data over smaller and smaller ranges of time. This article helped [this article](http://computationallyendowed.com/blog/2013/01/21/bounded-panning-in-d3.html). In their example, they only use scaleExtent([1,1]) so they aren't zooming but are just scrolling. I don't need that behavior now, but it might be useful in the future. However, they were also operating only on the x-axis. To do this, they only define an x-scale and not a y-scale when they set up the zoom behavior: d3.behavior.zoom().y(y).scaleExtent([1, 1]).on("zoom", zoom) vs d3.behavior.zoom().x(x).y(y).scaleExtent([1, 1]).on("zoom", zoom). [This Bostock example](http://bl.ocks.org/mbostock/4015254) also shows both panning and horizontal zooming. 

Now I'll give it a go!