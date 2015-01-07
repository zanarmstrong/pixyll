---
layout:     post
title:      Small Map of Continental US
summary:    Get map data from US government, transform with topojson, view with D3
categories: how-to
---

The goal of this post is to create a small map of the United States which can be used to select different cities which appear on the map. This will be driving another visualization with data about the selected city. For data I'll need the topojson file for the boundary of the United States, the lat/lon for the cities of interest, and the list of cities to show. 

#### Getting a Geo file and Visualizing it
I'll start by getting the shp file from the US Government for the [nation](https://www.census.gov/geo/maps-data/data/cbf/cbf_nation.html) or at [other levels of granularity](https://www.census.gov/geo/maps-data/data/tiger-cart-boundary.html).

If you have [topojson](https://github.com/mbostock/topojson/wiki/Installation) installed, you can do a simple transformation from SHP file to JSON file at the command line: 
	
	topojson -o us.json cb_2013_us_nation_20m.shp

You can then use [this example](http://bl.ocks.org/mbostock/4134057), replacing the file "/mbostock/raw/4090846/us.json" with new file (ie "us.json") and the object "topology.objects.land" with the appropriate name. If you used the nation file, the object will be "topology.objects.cb_2013\_us\_nation\_20m".

#### Making the map smaller

In order to make the map smaller and move it to a different location, I can introduce a projection object. In this case, I'll use the "albersUSA" projection, and include a scale factor and a translation. Note that the translation function takes an _array_ of coordinates. In the scale function, 1000 is no scale change and 200 shrinks the map.  

{% highlight javascript %}
var projection = d3.geo.albersUsa()
	.translate([100,100])
    .scale([200]);

var path = d3.geo.path().projection(projection);
{% endhighlight %}

#### Limit to Continental United States
However, I'd like to just focus on the continental United States. Therefore, I pulled the State-level data from the US Government website [here](https://www.census.gov/geo/maps-data/data/cbf/cbf_state.html). I also modified my topojson command in order to capture the name of each state. 

	topojson -o us.json --id-property NAME -- cb_2013_us_state_20m.shp 

The name of the state is coming from the .dbf file associated with the shp file. This .dbf file can be opened in Open Office or Microsoft Excel in order to identify the names of the columns to find the right property to pull out. More information on that [here](http://fileinfo.com/extension/dbf).

Now that I've identified the states in the json file, I can remove them before creating the path that draws the US as shown in the code below.

{% highlight javascript %}
d3.json("us.json", function(error, topology) {
  topology.objects.cb_2013_us_state_20m.geometries = 
  	topology.objects.cb_2013_us_state_20m.geometries.filter(
  		function(d){if(["Alaska", "Hawaii", "Puerto Rico"].indexOf(d.id) == -1){return d}}
  		)
  svg.append("path")
      .datum(topojson.feature(topology, topology.objects.cb_2013_us_state_20m))
      .attr("d", path);
});
{% endhighlight %}

Switching to "stroke: none" in the CSS part of the index.html file removes the lines between states. 

Now we have a small map of the continental United States.  

![](https://lh3.googleusercontent.com/-cXN3IcuM2KE/VK2qeByt70I/AAAAAAAAbg4/TEZ8vB083pA/w402-h234-no/thumbnail.png)

Code [here](http://bl.ocks.org/zanarmstrong/42dc0ba7b6b561d4d99e).






