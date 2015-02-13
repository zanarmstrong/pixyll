---
layout:     post
title:      Same Pixels, Different Picture
summary:    final SFPC project
categories: project
---

My final SFPC project, which I shared at the December SFPC open house, was about playing with how a set of pixels could paint a totally different picture when rearranged.  

Here is a gif of it in action. 

<img src="https://lh3.googleusercontent.com/PlY6sIs_FrtX0JxNV_ZGQDZDMGdvfs_12PIpOcWdpVDR=w1118-h416-no" alt="" height="200" width="400">

## Download and Try It Yourself
If you want to give it a try and you have a Mac, [you can download the app](https://www.dropbox.com/s/e9gt7qoyrdsvbc4/rearrangingPixels.zip?dl=0). Note, a few seconds after opening it will start to use your computer's camera as an input feed. Clicking "f" will toggle between the singly sorted and doubly sorted view.  Clicking any other key will switch between seed images on the right. 

## Rearranging Pixels
The project plays with the idea of taking information and changing the meaning through rearrangement.  It takes in a video feed from the computer's camera and displays that on the left side of the screen.  

**Every pixel on the left side shows up somewhere on the right side, with the same exact color.** You might not believe it when you see how different the images look, but it's guarenteed in the code. 

On the right, I first simply ordered in arcs radiating from the upper left corner. In other instances I used a seed image to determine the order of the brightness of the pixel on the right, so I was using the colors from the left image to sort-of paint the right image.  The colors from the left image are arranged based on the brightness of the right seed image, to create the resulting image.  

## Examples
A still example is here shown with simply sorting to seed right side and with an image as the seed. Sorry for the cheesiness of holding up my phone... it was the most colorful thing I had on hand when taking the screenshots. During the exhibit, I had colorful paper available to people could play with seeing how the image changed if they introduced more color to the input.  

Sorting to seed the right side:
![](../../../../../images/pixels2.png)

An image of an iguana seeds the right side:
![](../../../../../images/pixels1.png)

## Two modes: Single Sorting and Double Sorting

There are also two modes: single sorting and double sorting. In single sorting, only the seed image on the right is ordered by brightness. In double sorting, both images are sorted by brightness before mapping pixel colors from the left image onto the right image. In other words, the color of the 100th brightest pixel on the left is then applied to the 100th brightest pixel on the right. The seed image is easier to perceive with double-sorting, but we generally seem to perceive more color in the single sorting because continguous colors in the input are more likely to stay together with only single sorting. 

Single sorting: 
![](../../../../../images/pixels2.png)

Double sorting: 
![](../../../../../images/pixels3.png)

Single sorting with a flower input image: 
![](../../../../../images/pixel4.png)

Double sorting with a flower input image:
![](../../../../../images/pixels5.png)

## Exploring Color Perception

Even though every pixel on the left is somewhere in the image on the right, with the same exact color, the right image generally appears much more as shades of gray or near-gray.  What I'm guessing is happening is that in the source image, a blue-ish color will most likely be adjacent to another blue-ish color, creating a blueish area. When placed by brightness, now two pixels with similar brightness will likely be adjacent, even if one of them is redish and the other is blueish. These seem to blur in our eyes, therefore making the right image appear more grey than the left. Furthermore, when blue-ish pixels are together in the source image, we'll perceive them as blue even if some of them are actually more grey due to a shadow. When they are rearranged, we lose the context.

Moreover, in this example, the seeming green colors of the sweater is mostly lost to our perception in the second image. 

Zooming in on a small sections of the input image show similar hues, even with varied brightness. The first image is from the phone's cover and the second from my hand. 

![](../../../../../images/pixels6.png)

After resorting, hues are no longer as uniform though brightness is still fairly consistent. Ovearll the image looks more grey and pixelalled. Below we see an area of the flower that was painted with a lot of the phone's blue from the input image and another area of the flower that received a lot of the skin color.

![](../../../../../images/pixels7.png)

## So What?
While the raw "data" (set of colored pixels) is exactly the same on the right and the left, the data takes on completely different meaning when reordered. Even more, the reordering changes our perception of the colors so that it no longer even appears that both images contain the same information. Holding colorful objects in front of the camera and seeing the right image react convinces us that, yes, the pixels are the same as we see a set of hues appear or disappear.

In a more poetic level, because of context we seem to see the world as more colorful than it "really" is.  Which, perhaps, is a nice thing afterall.

