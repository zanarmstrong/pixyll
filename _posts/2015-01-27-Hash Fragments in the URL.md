---
layout:     post
title:      Hash Fragments in the URL
summary:    A reward for good state management
categories: tips
---

Hash fragments in the URL can be used to bookmark a particular view of an interactive visualization so that it can be shared. This is super useful, and enabling it is a reward for effectively managing the state of the visualization in your code.  

For example, consider the URL: [http://weather.zanarmstrong.com/#city=FARGO&metric=cloudCover&colored=1](http://weather.zanarmstrong.com/#city=FARGO&metric=cloudCover&colored=1)

To access the hash, assuming it's seperated by &: 

	window.location.hash.split("&")


Then parse the resulting array in order to set the state of the visualization to the one specified in the URL.   

To set a hash, write something like: 

	window.location.hash = "city=FARGO&metric=cloudCover&colored=1";

Clearly you can paste together text and variables to set this, based on whatever your current state is.







