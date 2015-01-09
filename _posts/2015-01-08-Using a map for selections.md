---
layout:     post
title:      City selection with a small map
summary:    Using a map rather than drop-down menu to select cities
categories: log
---

Today I added a small map to my [typical temperature](http://bl.ocks.org/zanarmstrong/raw/15558afddc79a52847bc/) visualization for city selection, replacing the drop-down menu. 

![](https://lh3.googleusercontent.com/-QBGAdCzTsXI/VK8dckfVymI/AAAAAAAAbiU/XB8Ua_FT3YA/w658-h284-no/Screen%2BShot%2B2015-01-08%2Bat%2B4.14.07%2BPM.png)

I cleaned up the code since it was getting a bit out of hand. In particular, I had more global variables than necessary and found that many of them could be removed by simply using classes more effectively.








