---
layout:     post
title:      Queue with D3
summary:    Using Queue for reading in data files is straightforward
categories: how-to
img: queue.png
---

I've known about [Queue.js](https://github.com/mbostock/queue) for a while, but finally used it for the first time today. It is an "asynchronous helper library". 

In short, reading in data is fundamental to data analysis. The typical way to read in a file in D3 is of the form:

	d3.json("path/to/file.json", function(error, json) {
  		if (error) return console.warn(error);
  		data = json;
  		visualizeit();
	}); 

as described by Bostock [here](https://github.com/mbostock/d3/wiki/Requests). However, often a visualization may require several different data files. This is especially true if maps are involved because you'll need a json file for the shape of the country or other geographic features. This can start to make the code look confusing if you need to read in multiple files, waiting for each one before acting on the data. Queue solves that. More importantly, it allows you to read in files in parallel. 

I used it for the first time today in [this project](http://bl.ocks.org/zanarmstrong/134b91959c2f7a7d22e4).

![](../../../../../images/queue.png)

I was inspired by reading [this tutorial](http://blog.webkid.io/multiple-maps-d3/) for another project I was working on where I wanted to use small multiple maps. 

[This explanation and bl.ocks example](http://giscollective.org/d3-queue-js/) are also quite useful. 





